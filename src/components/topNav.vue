<template>
  <div class="topnav">
    <div class="logo">LOGO</div>
    <div class="menu">
      <ul><li><router-link to="/">Home</router-link></li><li><router-link to="/doc">Doc</router-link></li></ul>
    </div>
  </div>
</template>
<style lang="scss" scoped>
  .topnav {
    display: flex;
    width: 100%;
    height: 80px;
    background: pink;
    border: 1px solid red;
    .logo {
      float: left;
      width: 100px;
      height: 80px;
      line-height: 80px;
    }
    .menu {
      ul {
        li {
          display: inline-block;
          width: 150px;
          height: 80px;
          line-height: 80px;
        }
      }
    }
  }
</style>