<template>
  <div class="topnav">
    <div class="logo" @click="toggleMenu">LOGO</div>
    <div class="menu">
      <ul><li><router-link to="/">Home</router-link></li><li><router-link to="/doc">Doc</router-link></li></ul>
    </div>
  </div>
</template>
<script lang="ts">
import { inject, Ref } from 'vue'
export default {
  setup() {
    const menuVisible = inject<Ref<boolean>>('menuVisible') // get
    console.log('topNav 获取的 menuVisible 为：' + menuVisible.value)
    const  toggleMenu = () => {
      menuVisible.value = !menuVisible.value
    }
    return { toggleMenu }
  },
 
}
</script>
<style lang="scss" scoped>
  .topnav {
    display: flex;
    width: 100%;
    height: 80px;
    background: pink;
    border: 1px solid red;
    position: relative;
    z-index: 10;
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