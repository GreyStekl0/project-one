<script setup>
const tech = [
  {
    img: {
      src:"/php.png",
      alt:"php"
    },
    name:"PHP"
  },
  {
    img: {
      src:"/laravel.png",
      alt:"Laravel"
    },
    name:"Laravel"
  },
  {
    img: {
      src:"/js.png",
      alt:"js"
    },
    name:"JavaScript"
  },
  {
    img: {
      src:"/Nuxt.js.png",
      alt:"Nuxt.js"
    },
    name:"Nuxt.js"
  },
  {
    img: {
      src:"/mySQL.png",
      alt:"mySQL"
    },
    name:"MySQL"
  },
  {
    img: {
      src:"/postgreSQL.png",
      alt:"postgreSQL"
    },
    name:"PostgreSQL"
  },
  {
    img: {
      src:"/api.png",
      alt:"RESTful API"
    },
    name:"RESTful API"
  },
  {
    img: {
      src:"/GitLab.png",
      alt:"GitLab"
    },
    name:"GitLab"
  },
]
</script>

<template>
  <section class="tech">
    <div class="container">
      <h2>
        Технологии
      </h2>
      <div class="row">
        <div class="col-6 col-md-4 col-lg-3"
        v-for="(item,index) in tech"
        :key="index">
          <div class="tech__Card">
            <div class="tech__Card-img-wrap">
              <img :src="item.img.src" :alt="item.img.alt">
            </div>
            <div class="tech__Card-name">
              {{ item.name }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>