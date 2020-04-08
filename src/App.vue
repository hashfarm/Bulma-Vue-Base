<template>
  <div id="app">

    <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a class="navbar-item">

      </a>

      <a role="button" class="navbar-burger" data-target="navMenu" aria-label="menu" aria-expanded="false">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>

      
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-start">
        <a class="navbar-item" v-on:click="component = 'main-vue'">
          Main
        </a>

        <a class="navbar-item" v-on:click="component = 'second-vue'">  
          Second
        </a>

      </div>
    </div>
  </nav>
   
   <transition name="component-fade" mode="out-in">
       <components v-bind:is="component"></components>
   </transition>

  </div>
</template>

<script>
import Main from "./components/Main.vue"
import Second from "./components/Second.vue"

export default {
  name: 'App',
  components: {
    'main-vue': Main,
    'second-vue': Second
  },
  data() {
    return {
      component: 'main-vue',
    }
  },
   methods: {
     afterEnter: function () {
     
     }
   }
  
}

document.addEventListener('DOMContentLoaded', () => {
  const $navbarBurgers = Array.prototype.slice.call(document.querySelectorAll('.navbar-burger'), 0);

  if ($navbarBurgers.length > 0) {
    $navbarBurgers.forEach( el => {
      el.addEventListener('click', () => {
        const $target = document.getElementById("navbarBasicExample");
        el.classList.toggle('is-active');
        $target.classList.toggle('is-active');

      });
    });
  }

});
</script>

