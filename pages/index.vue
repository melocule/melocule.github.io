<template lang="pug">
.flex.flex-col.grow.justify-between
  .flex.justify-self-center.justify-content-center.align-items-center.grow
    .hero
      .hero-content.flex-col(class='md:flex-row-reverse')
        img.max-w-sm.rounded-lg.shadow-2xl(src='../assets/photo.jpeg')
        .py-8(class='md:pr-12 md:py-0')
          h1.text-5xl I'm Melody Liu 👋
          p.py-6 Full stack developer for web and mobile. <br> I typically use React, Typescript, and Tailwind.
  footer-melo
</template>