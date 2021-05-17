<template>
  <div>
    
    <nav>
      <h1>Ongoing Projects</h1>
      <div class="projects-search">
        <input type="search" placeholder="Search History" name="search">
        <i class="fas fa-search"></i>
      </div>
    </nav>
    
    <div class="main">

      <div class="projects-nav">
        <hr>
        <span>{{info.length}} Projects</span>
      </div>

      <div class="projects-table">
        <div class="side-bar">
          <div class="header">
            <div class="item fixed-side">Project Name</div>
          </div>
          <div
            v-for= "project in info"
            :key= "project"
            class="project-list"
            >
            <div class="item fixed-side">{{project.project_name}}</div>
          </div>
        </div>

        <div class="projects">
          <div class="header">        
            
            <div class="item">Developer</div>
            <div class="item">Main Contractor</div>
            <div class="item">Area</div>
            <div class="item">State</div>
            <div class="item">Status</div>
            <div class="item">Sector</div>

          </div>
          <div
            v-for= "project in info"
            :key= "project"
            class="project-list"
            >

            <div class="item">{{project.developer}}</div>
            <div class="item">{{project.main_contractor}}</div>
            <div class="item">{{project.region}}</div>
            <div class="item">{{project.state}}</div>
            <div class="item status"
              v-bind:class='{"red" : project.status=="On hold",
              "blue" : project.status=="Site Clearing",
              "green" : project.status=="Completed",
              "orange" : project.status=="Under construction",
              "grey" : project.status=="Conceptual",
              "light-grey" : project.status=="Implementation"
              }'
              >
              {{project.status}}
            </div>
            <div class="item">{{project.sector}}</div>

          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios"

export default{
  name: "QuizTable",
  data(){
    return{
      info: '',
    }
  },
  mounted(){
    axios
      .get('https://244b8df3-7491-4cfd-a48b-267f19446372.mock.pstmn.io/')
      .then((res)=>{
        this.info = res.data.data
        console.log(res.data.data)
      })
      // .then(response => (this.info = response))
  }
}
</script>

<style>
</style>