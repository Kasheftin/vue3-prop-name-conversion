<template>
  <div>
    <button @click="$emit(props.eventName)">
      Click
    </button>
    {{ test }}
  </div>
</template>

<script setup lang="ts">
import { getCurrentInstance, computed } from 'vue'

const props = defineProps({
  eventName: {
    type: String,
    required: true
  }
})

const vm = getCurrentInstance()

const test = computed(() => {
  return vm?.vnode?.props ? Object.keys(vm.vnode.props).join(', ') : ''
})

</script>
