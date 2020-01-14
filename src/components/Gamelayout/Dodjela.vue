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
            broj: 0,
        }
        if(this.komb.length == 6){
                    this.komb=[];
                    this.tiket++;
                    this.$emit('add-komb', newKomb);
                }
      }
  }
}
</script>

<style scoped>
#kreiraj{
  display: inline-block;
  padding: 15px 25px;
  font-size: 24px;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  outline: none;
  color: black;
  background-color: orange;
  border: none;
  border-radius: 15px;
  box-shadow: 0 9px #999;
}

#kreiraj:hover {background-color: #FF7D03}

#kreiraj:active {
  background-color: #FF7D03;
  box-shadow: 0 5px #666;
  transform: translateY(4px);
}


</style>