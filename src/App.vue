<template>
  <main>
    <!-- Working: -->
    <PropsTest event-name="someEvent" @someEvent="handler" />
    <PropsTest event-name="someEvent" @SomeEvent="handler" />
    <PropsTest event-name="someEvent" @some-event="handler" />

    <PropsTest event-name="SomeEvent" @someEvent="handler" />
    <PropsTest event-name="SomeEvent" @SomeEvent="handler" />
    <PropsTest event-name="SomeEvent" @some-event="handler" />

    <PropsTest event-name="some-event" @someEvent="handler" />
    <PropsTest event-name="some-event" @SomeEvent="handler" />
    <PropsTest event-name="some-event" @some-event="handler" />

    <PropsTest event-name="someEvent" :onSomeEvent="handler" />
    <PropsTest event-name="SomeEvent" :onSomeEvent="handler" />
    <PropsTest event-name="some-event" :onSomeEvent="handler" />

    <br>
    <!-- Non Working: -->
    <PropsTest event-name="someEvent" :on-some-event="handler" />
    <PropsTest event-name="SomeEvent" :on-some-event="handler" />
    <PropsTest event-name="some-event" :on-some-event="handler" />

  </main>
</template>

<script setup lang="ts">
import PropsTest from './PropsTest.vue'

const handler = () => {
  console.log('handler')
}
</script>

