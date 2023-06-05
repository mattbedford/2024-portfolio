<template>
  <div class="main">
    <h1 id="projects">My work</h1>
    <my-projects v-for="(item, index) in projects" :key="index" :single="item"/>

    <div class="photo">
      <img class="matt-picture" src="@/assets/matt-picture.webp" />
    </div>
    <h1 id="about">All about me and my work</h1>
      <p>I'm a full stack web developer working with PHP, JavaScript, Node and Vue.js.
      (Plus my html and css are top-notch).</p>
      <p>I have been developing on and off for over ten years, finally going full-time in 2019. In that time I've gained a lot of experience on Wordpress and Woo Commerce installations as well 
        as Shopify/Liquid, a little Jamstack (Netlify) and a few other CMS's.
      </p>
      <p>What I love most about my work is integrating sites with different API- and webhook-driven services,
        such as Stripe, HubSpot, Zoho CRM, WP REST and any others you can dream of: making systems talk to each other in pursuit of efficiency.</p>
      <p>Before being a full-time dev, I worked in digital marketing and I ran my own agency for ten years. 
        These two things help me understand the bigger picture and make sure that all my coding projects are
        aligned with the wider business goals.
      </p>
  </div>
</template>

<script>
import myProjects from './my-projects.vue'
export default {
  components: { myProjects },

    name: "App",
    data: () => ({
      projects: null
     }),
    mounted: function() {
      this.fetchProjects()
    },
    methods: {
    fetchProjects: async function () {
        fetch("https://matt-backend.sh1.hidora.net/wp-json/wp/v2/projects/?per_page=8&order=asc")
            .then(response => response.json())
            .then(data => this.projects = data)
      },
    }

}
</script>
