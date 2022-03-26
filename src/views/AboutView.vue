<template>
  <div class="about">
    <h3>This is AboutView</h3>
    <TabComponent msg="This is a TabComponent" />
  </div>
</template>

<script>
// @ is an alias to /src
import TabComponent from '@/components/TabComponent.vue'

export default {
  name: 'AboutView',
  components: {
    TabComponent
  }
}
</script>

