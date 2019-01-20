<template>
  <div class="floating-panel">
    <img alt="Vue logo" src="../assets/logo_visualizeBigO.jpg" style="width:200px;height: auto;">
    <ul class="menu-list">
      <a href="#concept" class="menu-link">
        <li class="menu-item">
          CONCEPT
        </li>
      </a>
      <a href="#sorting" class="menu-link">
        <li class="menu-item">
          SORTING
        </li>
      </a>
      <a href="#contact" class="menu-link">
        <li class="menu-item">
          CONTACT
        </li>
      </a>
    </ul>
  </div>
</template>
<script>
  export default {
    name: 'Menu',
    props: {
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.floating-panel {
  background-color: #083248;
  color: #FFF;
  font-family: Roboto, Arial, sans-serif;
  height: 100vh;
  /*margin-top: 60px;*/
  position: fixed;
}
.menu-list {
  padding: 0px;
}
.menu-link {
  text-decoration: none;
  color: #FFF;
  cursor: pointer;
}
.menu-item {
  font-size: 18px;
  list-style-type: none;
  padding-bottom: 10px;
  padding-top: 10px;
}
</style>