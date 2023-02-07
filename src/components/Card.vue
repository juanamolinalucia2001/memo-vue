<template>
  <div v-if="card.matched" class="card matched">
  </div>

  <div v-else class="card" @click="clickHandler">
    <img v-if="card.open" :src="card.image" />
    <div v-else class="not-opened">?</div>
  </div>
</template>

<script>
export default {
    neme:'Card',
  props: {
    card: Object
  },
  data: () => {
    return {
    }
  },
  methods: {
    clickHandler: function() {
      if (!this.card.open && !this.card.matched) {
        this.$parent.$emit('onCardOpen', this.card)
      }
    }
  }
}
</script>

<style>
.card {
  display: inline-block;
  margin: 15px;
  width: 130px;
  height: 130px;
  vertical-align: top;
  cursor: pointer;
}
.card .not-opened {
  border: 3px solid black;
  height: 100%;
  text-align: center;
  font-size: 32px;
  padding-top: 25px;
}
.card.matched {
  cursor: default;
}
.card img {
  display: inline-block;
  width: 100%;
  height: 100%;
}
</style>