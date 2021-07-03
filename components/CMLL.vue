<template>
  <div class="cmll">
    <div class="cmll__pattern">
      <template v-for="(cell, index) in patternJoin">
        <div :key="index" class="cmll__cell" :class="cell"></div>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CMLL',
  props: {
    cmll: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    patternJoin() {
      return [
        ...this.cmll.pattern[0],
        ...this.cmll.pattern[1],
        ...this.cmll.pattern[2],
        ...this.cmll.pattern[3],
        ...this.cmll.pattern[4],
      ]
    },
  },
}
</script>

<style lang="scss">
.cmll {
  $coef: 4;
  &__pattern {
    display: grid;
    column-gap: 0.5rem;
    row-gap: 0.5rem;
    grid-template-columns: $coef * 0.2rem $coef * 1rem $coef * 1rem $coef * 1rem $coef * 0.2rem;
    grid-template-rows: $coef * 0.2rem $coef * 1rem $coef * 1rem $coef * 1rem $coef * 0.2rem;
  }
  &__cell {
    &:not(.transparent) {
      outline: 0.125rem solid rgb(64, 64, 64);
    }
    &.green {
      background-color: green;
    }
    &.red {
      background-color: red;
    }
    &.blue {
      background-color: blue;
    }
    &.orange {
      background-color: orange;
    }
    &.white {
      background-color: white;
    }
    &.yellow {
      background-color: yellow;
    }
    &.grey {
      background-color: rgb(64, 64, 64);
    }
  }
}
</style>
