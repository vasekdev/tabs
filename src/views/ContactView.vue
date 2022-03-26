<template>
  <div class="about">
    <h3>This is ContactView</h3>
    <p>ContactView paragraph with a <a href="javascript:void(0)" @click="addWindow('test-url','test-value')">link</a>.
    </p>
    <ContactComponent msg="This is a ContactComponent" />
  </div>
</template>

<script>
// @ is an alias to /src
import ContactComponent from '@/components/ContactComponent.vue'

export default {
  name: 'ContactView',
  components: {
    ContactComponent
  },
  methods: {
     addWindow: function(url, windowValue){
        console.log(" url: " + url + 'addWindow: ' + windowValue);
     }
  }
}
</script>

