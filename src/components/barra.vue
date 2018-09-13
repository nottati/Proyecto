<template>
<nav class="navbar is-fixed-top is-info" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
      <div>
    <a class="navbar-item" href="">
      <img src="https://78.media.tumblr.com/d02dcc7a8e8cd349fc08f84572ba14ab/tumblr_pecsd4FsFi1qftou2o1_250.jpg" alt="Tasky" width="25" height="28">
    </a>
      </div>
      <div>
          <a class="navbar-item" href="">
          <p> Trello Dos </p>
          </a>
      </div>
       <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>
  </div>
</nav>
</template>

<script>
export default {
  name: 'barra',
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.navbar-brand {
    margin-left: 50%;
    margin-right: 50%
} 

p {
    color: aliceblue
}

</style>