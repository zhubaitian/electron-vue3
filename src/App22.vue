<template>
  <div id="vue-root" class="wrapper">
    <suspense>
      <router-view v-slot="{ Component }">
        <transition>
          <component :is="Component" />
        </transition>
      </router-view>
    </suspense>
  </div>
</template>

<script lang="ts">
import { defineComponent, Suspense } from "vue";

export default defineComponent({
  name: "App",
  components: {
    
  },
  computed: {
    showFooter() {
      console.log("this.$route:", this.$route);
      // return false
      const showFooter =
        this.$route.path.split("/").length < 3 &&
        this.$route.path != "/demo" &&
        this.$route.path != "/login";
      console.log("showFooter:", showFooter);
      return showFooter;
    },
  },
});
</script>

<style>
html,
body {
  height: 100%;
  width: 100%;
  /*padding-top: 0px !important;*/
  /*overflow-x: hidden;*/
  background-color: #f5f5f5;
  /*color: #333;*/
  /*border: none;*/
  /*text-*/
  overflow: hidden;
  -webkit-overflow-scrolling: touch;

  -webkit-user-select: none;
  user-select: none;
  -webkit-touch-callout: none;
}

#app,
#vue-root {
  height: 100%;
  width: 100%;
}
/* .van-tabbar {
  height: 3.5rem;
  font-size: 1rem;
  display: flex;
  align-items: center;
}

.van-tabbar-item {
  height: 3rem;
}

.van-tabbar-item__icon {
  font-size: 1.8rem;
}

.van-tabbar-item__text {
  font-size: 0.8rem;
} */

.van-pull-refresh__track {
  min-height: calc(100vh);
}
</style>