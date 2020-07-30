<template>
  <div>
    <topNav></topNav>
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
      <main>主内容</main>
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
 .content {
   aside {
     width: 150px;
     background: lightblue;
     color: black;
     padding: 16px;
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
      padding-top: 70px;
    }
   }
 } 
</style>