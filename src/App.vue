<script setup>
import { ref, reactive } from 'vue'


const activeIndex = ref(0);

const images = [
  {
    image: "https://images.unsplash.com/photo-1682685797769-481b48222adf?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60",
    title: "First Image"
  },
  {
    image: "https://images.unsplash.com/photo-1682695794816-7b9da18ed470?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60",
    title: "Second Image"
  },
  {
    image: "https://images.unsplash.com/photo-1682685797661-9e0c87f59c60?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60",
    title: "Third Image"
  },
  {
    image: "https://plus.unsplash.com/premium_photo-1666963323736-5ee1c16ef19d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDE2fHx8ZW58MHx8fHx8&auto=format&fit=crop&w=1024&q=60",
    title: "Fourth Image"
  }
]
</script>

<template>
<div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li @click="activeIndex = index" data-target="#carouselExampleIndicators" v-for="(image,index) in images" :key="index" :class="index==activeIndex?'active':''"></li>
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img height="500" class="d-block w-100" :src="images[activeIndex].image" alt="First slide">
      <div class="carousel-caption d-none d-md-block">
       <h5>{{ images[activeIndex].title }}</h5>
  </div>
    </div>
  </div>
  <a @click.prevent="0 == activeIndex? activeIndex = (images.length) - 1:activeIndex--" class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a @click.prevent="(images.length) - 1 == activeIndex ? activeIndex = 0:activeIndex++" class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
</template>
