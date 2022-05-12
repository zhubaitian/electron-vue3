<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
     <button @click="gotoAbout">测试路由跳转</button>
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
   
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import { useRouter } from "vue-router";

export default defineComponent({
  name: 'HomeView',
  components: {
    HelloWorld,
  },
  async setup() {
     const router = useRouter();
     console.log('router:', router)
    function gotoAbout() {
       router.push('/about')
    }

    return {
      gotoAbout,
    }
  }

});
</script>
