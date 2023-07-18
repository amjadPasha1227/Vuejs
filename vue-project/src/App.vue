<template>
    <div class="main_wrapper">
      <SideBar />
      <HeaderComp />
      <button @click="count++">{{ count }}</button>
    </div>
</template>

<script>
  import SideBar from './components/SideBar.vue'
  import HeaderComp from './components/Header.vue'
  export default {
    components: {
      HeaderComp,
      SideBar
    },
    data() {
      return {
        count: 0
      }
    },
    // `mounted` is a lifecycle hook which we will explain later
    mounted() {
      // `this` refers to the component instance.
      console.log(this.count) // => 1

      // data can be mutated as well
      this.count = 0
    }
  }
</script>
