<template>
  <div class="home">
    <CMLL v-for="(c, index) in cmll" :key="index" :cmll="c" />
  </div>
</template>

<script>
import { mapState } from 'vuex'
import CMLL from '@/components/CMLL.vue'
export default {
  name: 'Home',
  components: {
    CMLL,
  },
  computed: {
    ...mapState('cmll', {
      cmll: (state) => state.cmll,
    }),
  },
}
</script>
