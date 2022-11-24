<template lang="pug">
header.pt-12.pb-4
  div.navbar.py-0.px-14
    .flex-1 
      a(href=".").btn.btn-ghost.normal-case.text-4xl.fancy-font ml.
    .flex-none 
      ul.menu.menu-horizontal
        li
          NuxtLink(to="/resume") Resume
        li 
          a(href="mailto: melody.liu.2@gmail.com" target="_blank") Contact
</template>

<style>
.fancy-font {
    font-family: Lobster, sans-serif;
}
</style>