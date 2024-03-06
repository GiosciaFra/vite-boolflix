<script>
import AppMain from './components/AppMain.vue'
import axios from 'axios';

export default {
  components: {
    AppMain,
  },

  data() {
    return {
    }
  },
}
</script>

<template>
    <div class="container">
        <AppMain></AppMain>
    </div>
</template>

<style lang="scss">
@use './styles/general.scss' as *
</style>
