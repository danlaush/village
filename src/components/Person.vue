<template>
  <span>{{ first ? null : ', ' }}<span class="name" @click="setActive" :class="{
      'active': active,
      'connected': connected
    }">{{ name }}</span>
  </span>
</template>

<script>
export default {
  props: {
    name: {
      type: String
    },
    connections: {
      type: Array
    },
    active: {
      type: Boolean
    },
    connected: {
      type: Boolean
    },
    first: {
      type: Boolean
    }
  },
  methods: {
    setActive() {
      this.$emit('setActive', this)
    }
  }
}
</script>

<style lang="scss" scoped>
.name {
  cursor: pointer;
}

.active {
  color: red;
}

.connected {
  color: orange;
}
</style>
