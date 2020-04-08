<template>
  <div class="Main">
      <form style="padding-top: 1em; padding-left: 1em;">
        <button class="button" type="button" id="TopButton1" v-on:click="component = 'MainP1-vue'">Page 1</button>
        <div class="divider"/>
        <button class="button"  type="button" id="TopButton2" v-on:click="component = 'MainP2-vue'">Page 2</button>
      </form>

        <transition name="component-fade" mode="out-in">
          <components v-bind:is="component"></components>
       </transition>

  </div>
</template>

<script>

import MainP1 from "./subcomponents/Main/MainP1.vue"
import MainP2 from "./subcomponents/Main/MainP2.vue"

export default {
  name: 'App',
  components: {
    'MainP1-vue': MainP1,
    'MainP2-vue': MainP2
  },
  data() {
    return {
      component: 'MainP1-vue'
    }
  }
}

</script>

<style scoped lang="scss">

  @import '../assets/MainPanel.scss';

</style>
