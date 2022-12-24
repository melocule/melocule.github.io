<template lang="pug">
body.flex.flex-col.h-screen.w-screen
  nav-bar
  .bee.z-10(ref='bee')
    img(src='~assets/bee.png', width='25px')
  Nuxt
</template>


<script>
import { gsap } from 'gsap/all'
export default {
  mounted() {
    const bee = this.$refs.bee
    gsap.set(bee, { xPercent: -50, yPercent: -50 }) // Set the anchor of the bee to the center
    const pos = { x: 0, y: 0 } // Spawn at upper left
    const size = 25
    const speed = 0.1
    const maxSpeed = 20
    const bounceHeight = 1
    const bounceSpd = 10
    const distance = { x: 10, y: 10 }
    const fpms = 60 / 1000
    const xSet = gsap.quickSetter(bee, 'x', 'px')
    const ySet = gsap.quickSetter(bee, 'y', 'px')

    const contain = (n, min, max) => {
      return Math.max(Math.min(n, max), min)
    }

    const mouse = { x: pos.x, y: pos.y }
    window.addEventListener('mousemove', (e) => {
      mouse.x = contain(e.x, distance.x + size, window.innerWidth + distance.x)
      mouse.y = contain(
        e.y,
        distance.y + bounceHeight * 3.1415 + size,
        window.innerHeight + distance.y
      )
    })

    gsap.ticker.add((time, deltaTime) => {
      const delta = deltaTime * fpms
      const dt = 1.0 - Math.pow(1.0 - speed, delta)

      pos.x += contain((mouse.x - pos.x - distance.x) * dt, -maxSpeed, maxSpeed)
      pos.y += contain(
        (mouse.y - pos.y - distance.y) * dt +
          bounceHeight * Math.sin(time * bounceSpd),
        -maxSpeed,
        maxSpeed
      )
      xSet(pos.x)
      ySet(pos.y)
    })
  },

  methods: {},
}
</script>


<style>
.bee {
  position: fixed;
  height: 50px;
  width: 50px;
  top: 0;
  left: 0;
  pointer-events: none;
}
</style>
