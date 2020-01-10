<template>
    <div id="dodjela">
        <button  id="kreiraj" v-on:click="kreiraj">Kreiraj tiket</button>
    </div>
</template>

<script>
export default {
  name: 'Dodjela',
  data: function(){
      return{
          komb: [],
          tiket: 1,
      }
  },
  methods:{
      kreiraj: function(){
          this.komb=[];
          var br;
          for(let i=0;i<6;i++){
              br=(Math.floor(Math.random()*48)+1);
              if(!this.komb.includes(br)){
                this.komb.push(br);
                                  }else{
                --i;}
          }
        var newKomb={
            idtiketa: this.tiket,
            kombinacija: this.komb,
        }
        this.tiket++;
        this.$emit('add-komb', newKomb);
      }
  }
}
</script>

<style>

</style>