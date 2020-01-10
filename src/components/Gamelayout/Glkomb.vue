<template>
<div class="glkomb">
    <p>{{broj}}</p><br>
    <p>{{konacniniz[0]}}</p>
    <p>{{konacniniz[1]}}</p>
    <p>{{konacniniz[2]}}</p>
    <p>{{konacniniz[3]}}</p>
    <p>{{konacniniz[4]}}</p>
    <p>{{konacniniz[5]}}</p>
    <p>{{konacniniz[6]}}</p>
    <p>{{konacniniz[7]}}</p>
  </div>
</template>

<script>
export default {
    data(){
        return{
            izvuceno: [],
            tajmer: 5,
            broj: "",
            i: 0,
            konacniniz: []
        }
    },
methods:{
    odborjavanje: function()
        {
            if(this.tajmer > 0 && this.i<this.izvuceno.length + 1 )
                {
                    setTimeout(()=>{
                        this.tajmer -= 1;
                        this.odborjavanje();
                    },1000)
                }
            else
                {
                    this.broj = this.izvuceno[this.i];
                    this.i += 1;
                    if(this.i != this.izvuceno.length)
                        {
                            this.tajmer = 5;
                          
                            this.odborjavanje();
                        }
                    this.konacniniz.push(this.broj);

                }
            
        },
    brojevi: function()
        {
            var temp;
            this.izvuceno = [];
            for(let j=0;j<8;j++)
                {
                    temp = Math.floor(Math.random()*48)+1;
                    if(!this.izvuceno.includes(temp))
                        {
                            this.izvuceno.push(temp);
                        }
                    else
                        {
                            --j;
                        }
                }
        }
},
mounted: function()
    {

        this.brojevi();
        this.odborjavanje();
    }
}

</script>

<style>

</style>
