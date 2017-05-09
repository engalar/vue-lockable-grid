<template>
  <div>
    <section style="background-color: yellow">
      {{plan}}
    </section>
    <section style="background-color: #0099ff">
      {{out}}
    </section>
  </div>
</template>
<script>
  export default {
    name: 'ics-cell',
    data () {
      return {}
    },
    methods: {},
    props: [
      'plan',
      'out'
    ]
  }
</script>
<style scoped>

</style>
