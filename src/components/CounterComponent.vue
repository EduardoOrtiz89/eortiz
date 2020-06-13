<template>
  <div class="flex items-center">
    <div>
      <button class="w-16 px-4 py-2 text-5xl text-white rounded bg-nord-1 hover:bg-nord-2" @click="decrement">-</button>
    </div>
    <span class="w-32 ml-8 text-5xl text-center">{{ count }}</span>
    <button class="w-16 px-4 py-2 ml-8 text-5xl text-white rounded bg-nord-1 hover:bg-nord-2" @click="increment">+</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    },
    decrement() {
      this.count--
    }
  }
}
</script>
