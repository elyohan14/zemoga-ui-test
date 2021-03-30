<template>
  <q-scroll-area horizontal style="width: 320px; height: 300px;" :thumb-style="thumbStyle" :bar-style="barStyle">
    <div class="row no-wrap">
      <q-card v-for="(item, index) in users" :key="index" :style="`width: 300px; height: 300px; background-image: url('/img/${item.picture}');`">
        <div class="row" style="position: absolute; top: 32%;">
          <q-btn :style="`background: ${item.thumb_color}; width: 30px; height: 30px; left: 0.26%;`">
            <q-icon :name="item.thumb_icon" color="white"/>
          </q-btn>
          <p class="ellipsis user-name color-white" >{{ item.name }}</p>
        </div>
        <q-card-section style="position: absolute;top: 40%;">
          <span class="ellipsis-2-lines user-description color-white">{{ item.description }}</span>
          <span class="ellipsis-2-lines user-ago"><b>{{ item.time_ago }} in {{ item.category }}</b></span>
        </q-card-section>                
        <div class="row align-center" style="position: absolute; top: 65%; left: 12%">
          <q-btn style="background: rgba(60, 187, 180, 0.8);">
            <q-icon name="thumb_up" color="white"/>
          </q-btn>
          <q-btn style="background: #FBBD4A;">
            <q-icon name="thumb_down" color="white"/>
          </q-btn>
          <div class="vote-button">
            <p class="vote-button-text">Vote now</p>
          </div>
        </div>
        <div class="row text-white">
          <div :style="`background: rgba(60, 187, 180, 0.6); position: absolute; bottom: 0%; width: ${item.votes.positive_percent}%; height: 36px;`">
            <q-icon class="q-pa-sm" name="thumb_up" color="white" size="sm"/>
            <b style="font-family: Lato;font-size: 18px;line-height: 22px;">{{ item.votes.positive_percent }}%</b>
          </div>
          <div :style="`background: rgba(249, 173, 29, 0.6); position: absolute; bottom: 0%; left: ${item.votes.positive_percent}%; width: ${item.votes.negative_percent}%; height: 36px; text-align: end`">
            <b style="font-family: Lato;font-size: 18px;line-height: 22px;">{{ item.votes.negative_percent }}%</b>
            <q-icon class="q-pa-sm" name="thumb_down" color="white" size="sm"/>        
          </div>
        </div>
      </q-card>
    </div>
  </q-scroll-area>
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
<style>
.user-name {
  max-width: 230px;
  font-family: Lato;
  font-size: 30px;
  line-height: 36px;
}
.user-description {
  font-family: Lato;
  font-size: 15px;
  line-height: 18px;
  
}
.user-ago {
  font-family: Lato;
  font-style: normal;
  font-weight: normal;
  font-size: 15px;
  line-height: 18px;
  text-align: end;
  color: #FFFFFF;
}
.vote-button {
  width: 107px;
  background: rgba(0, 0, 0, 0.6);
  border: 1px solid #FFFFFF;
  box-sizing: border-box;
}
.vote-button-text {
  font-family: Lato;
  font-size: 15px;
  line-height: 18px;
  margin: revert;
  text-align: center;
  color: #FFFFFF;
}
.color-white {
  color: #FFFFFF;
}
</style>
