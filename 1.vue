<template>
    <div>
      <circle-bubble v-for="(bubble, index) in bubbles" :key="index" :text="bubble.text" @click="showBubble(bubble)" />
      <bubble-modal v-if="selectedBubble" :text="selectedBubble.text" @close="selectedBubble = null" />
    </div>
  </template>
  
  <script>
  import CircleBubble from './CircleBubble.vue'
  import BubbleModal from './BubbleModal.vue'
  
  export default {
    components: {
      CircleBubble,
      BubbleModal
    },
    data() {
      return {
        bubbles: [
          { text: '气泡1' },
          { text: '气泡2' },
          { text: '气泡3' }
        ],
        selectedBubble: null
      }
    },
    methods: {
      showBubble(bubble) {
        this.selectedBubble = bubble
      }
    }
  }
  </script>
  