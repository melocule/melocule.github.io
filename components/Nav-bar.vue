<template lang="pug">
header.pt-12.pb-4
  .navbar.py-0.px-14
    .flex-1 
      a.btn.btn-ghost.normal-case.text-4xl.fancy-font(href='.') &#60;ml/&#62;
    .flex-none 
      ul.menu.menu-horizontal
        li
          NuxtLink(to='/resume') Resume
        li 
          a(href='mailto: melody.liu.2@gmail.com', target='_blank') Contact
</template>

<style>
.fancy-font {
  font-family: Lobster, sans-serif;
}
</style>