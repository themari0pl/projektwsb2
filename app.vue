<script setup>
const menu = [
  {
    "name": "Home",
    "to":  "/"
  },
  {
    "name": "About",
    "to":  "/about"
  },
  {
    "name": "Team",
    "to":  "/team"
  },
  {
    "name": "Testimonial",
    "to":  "/Testimonial"
  },
  {
    "name": "Booking",
    "to":  "/booking"
  },
]

</script>
<template>
      <TopNav :items-menu="menu"/>
      <NuxtPage/>
      <Footer/>   
</template>
