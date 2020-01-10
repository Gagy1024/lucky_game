<template>
    <div class="counter">
        <p>{{startTajmer}}</p>
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