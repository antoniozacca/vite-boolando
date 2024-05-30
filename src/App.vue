<script>
import headers from './components/headerApp.vue'
import mains from './components/mainApp.vue'
  export default {
    name: "myApp",
    components: {
      headers,
      mains,
    }

}



</script>

<template>
  <headers></headers>
  <mains class="mains"></mains>
</template>

<style scoped>
.mains{
  margin-top: 40px;
}
</style>
