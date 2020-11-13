<template>

  <span class="ClickToReveal" @click="onClick">

    <span v-if="!revealed">{{ text }}</span>

    <slot v-if="revealed"></slot>

  </span>

</template>

<script>

export default {

  name: 'ClickToReveal',

  props: {
    text: {
      type: String,
      default: "Click to reveal."
    }
  },

  data()
  {
    return {
      revealed: false
    }
  },

  methods: {

    onClick()
    {
      console.log(this.$slots)

      if (!this.revealed && !!this.$slots.default)
      {
        this.revealed = true;
      }
    }
  }

}

</script>

<style scoped>

.ClickToReveal {
  cursor: pointer;
}

</style>
