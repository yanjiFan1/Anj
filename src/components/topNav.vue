<template>
  <div class="topnav">
    <div class="logo">LOGO</div>
    <div class="menu">
      <ul><li>菜单1</li><li>菜单2</li></ul>
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