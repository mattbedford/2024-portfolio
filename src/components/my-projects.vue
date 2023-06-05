<template>
        <div class="project-card project" @click="goToProject(single.id)">
        <div class="feat-image" :style="{ backgroundImage: 'url(' + single.main_pic.guid + ')' }" />
        <div class="texts">
            <h3>{{single.client}}</h3>
            <p>{{single.overview}}</p>
            
        </div>
        </div>
  </template>
  
  <script>
  import { RouterLink, RouterView } from 'vue-router'
  import router from '../router'

  export default {
      props: ['single'],
      data() {
        return {
            name: 'myProjects',
            projects: null,
        }
      },
      methods: {
            goToProject(projId) {
                router.push({ name: 'projects', params: { id: projId } })
            }
        }
  }  
  </script>
  
  <style>
  .projects-box {
      display:flex;
      flex-wrap:wrap;
      justify-content:flex-start;
      gap:20px;
  }
  .project-card {
      flex:0 1 48%;
      width:48%;
      cursor:pointer;
  }
  .project-card .feat-image {
      width:100%;
      height:300px;
      background-size:cover;
      background-position:center;
      background-repeat:no-repeat;
  }
  .project-card .texts {
      background:#e2e2e2;
      padding:10px 20px;
      min-height:100px;
      padding-bottom:10px;
  }
  .project-card .texts p {
      margin:5px 0px;
  }
  
  </style>