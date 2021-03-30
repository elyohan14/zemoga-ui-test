<template>
  <div>
    <div class="row">
      <p class="col-sm-11 text" >Previous Rulings</p>
      <div class="col-sm-1">
        <q-select :options="options" v-model="option" emit-value map-options/>
      </div>
    </div>
    <tablet-list v-if="option === 1" :users="users"/>
    <tablet-grid v-else :users="users"/>
  </div>
</template>
<script>
import TabletList from 'components/TabletList'
import TabletGrid from 'components/TabletGrid'
export default {
  components: {
    TabletList,
    TabletGrid
  },
  props: ['users'],
  data () {
    return {
      option: 1,
      options: [
        {
          label: 'List',
          value: 1
        },
        {
          label: 'Grid',
          value: 0
        }
      ]
    }
  }
}
</script>
<style>
.text {
  font-family: Lato;
  font-weight: 300;
  font-size: 24px;
  line-height: 29px;
  color: #464646;
}
</style>