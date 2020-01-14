<template>
    <div class="counter">
        <div id="krug"><p id="krugtekst">{{startTajmer}}</p></div>
        <router-view />
    </div>
</template>

<script>
export default {
    data ()
        {
            return{
                startTajmer: 60
            }
        },
    methods:
        {
            brojanje: function()
                {
                    if(this.startTajmer > 0)
                        {
                            setTimeout(()=>{
                                this.startTajmer -= 1;
                                this.brojanje();
                            },1000)
                        }
                }
        },
    mounted: function()
        {
            this.brojanje();
        }
}
</script>
<style>
#krug
    {
        width: 300px;
        height: 300px;
        border-radius: 300px;
        background-color: orange;
        text-align: center;
        font-size: 150px;
        margin-left: 37vw;
    }
#krugtekst
    {
        padding: 60px;
        color: black;
    }
</style>