<template>
  <div class="g-doc">
    <topNav></topNav>
    <div class="content-box">
      <div class="content">
        <aside v-if="menuVisible">
          <h2>组件列表</h2>
          <ol>
            <li><router-link to="/doc/switch">Switch 组件</router-link></li>
            <li><router-link to="/doc/button">Button 组件</router-link></li>
            <li><router-link to="/doc/dialog">Dialog 组件</router-link></li>
            <li><router-link to="/doc/tabs">Tabs 组件</router-link></li>
          </ol>
        </aside>
        <main><router-view /></main>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import TopNav from '../components/topNav.vue'
import { inject, Ref } from 'vue'
export default {
  components: {
    TopNav
  },
  setup() {
    const menuVisible = inject<Ref<boolean>>('menuVisible') // get
    console.log('topNav 获取的 menuVisible 为：' + menuVisible.value)
    return { menuVisible }
  }
}
</script>
<style lang="scss" scoped>
.g-doc {
  position: relative;
  width: 100%;
  height: 100%;
}
.content-box {
  position: absolute;
  top: 80px;
  bottom: 0;
  width: 100%;
  background: chocolate;
}
 .content {
   display: flex;
   justify-content: space-between;
   background: lightcyan;
   width: 100%;
   height: 100%;
   aside {
     width: 150px;
     height: 100%;
     background: lightblue;
     color: black;
     padding: 16px;
     margin-right: -150px;
     box-sizing: border-box;
     ol {
       li { 
         text-align: left;
         color: black;
       }
     }
     @media (max-width: 500px) {
      position: fixed;
      top: 0;
      left: 0;
      padding-top: 86px;
    }
   }
   main {
     margin-left: 150px;
     float: right;
     width: 100%;
     height: 100%;
     overflow: scroll;
     @media (max-width: 500px) {
      margin-left: 0;
    }
   }
 } 
</style>