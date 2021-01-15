<template>
  <div class="main-nav">
    <router-link :to="{name: 'Home'}">Home</router-link>
    <router-link :to="{name: 'AddProject'}">Add a new Project</router-link>
  </div>
</template> 

<script>
export default {

}
</script>

<style>
    .main-nav{
       text-align: center;
       margin: 40px auto;
    }
    .main-nav a{
        text-decoration: none;
        margin: 0 10px;
        display:inline-block;
        color: #999;
        font-size:18px
    }
    a.router-link-active{
        padding-bottom:4px;
        border-bottom: 2px solid #00ce89;
    }

</style>