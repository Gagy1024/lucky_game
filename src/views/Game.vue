<template>
  <div id="game">
    <Dodjela v-on:add-komb="addKomb" />
    <counter v-on:load="Counter" />
  </div>
</template>

<script>
import Dodjela from './../components/Gamelayout/Dodjela.vue';
import Counter from './../components/Counter.vue';

export default {
  name: 'Game',
  components:{
    Dodjela,
    Counter,
  },
  data: function() {
    return {
      korKombinacije: [],
    }
  },
  methods:{
    addKomb:function(newKomb){
      this.korKombinacije.push(newKomb);
    }
  }
}
</script>

<style>
</style>