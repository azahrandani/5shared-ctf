<template>
  <div class="home container d-flex align-items-center">
    <Welcome msg="Welcome to 5Shared CTF!"/>
  </div>
</template>

<script>
import Welcome from '@/components/Welcome.vue'

export default {
  name: 'Home',
  components: {
    Welcome
  }
}
</script>
