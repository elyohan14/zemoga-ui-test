<template>
  <h1>Vista Tablet List en proceso</h1>
</template>

<script>
export default {
  props: ['users'],
  data () {
    return {
      barStyle: {
        right: '2px',
        borderRadius: '1px',
        backgroundColor: 'rgb(2, 123, 227, 0)',
        width: '1px',
        opacity: 0.2
      },
      thumbStyle: {
        right: '4px',
        borderRadius: '5px',
        backgroundColor: 'rgb(2, 123, 227, 0)',
        width: '5px',
        opacity: 0.75
      }
    }
  }
}
</script>
