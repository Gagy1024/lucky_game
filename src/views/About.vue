<template>
  <div class="about">
    <Header />
    <div id="tekst">
      <p>
      Nesto o aplikaciji....<br/>
      Pravila:<br/>...pravila??...<br/>
      WebApp "Lucky Game" jer razvijena od strane Dragana Todorovica, Nenada Sarovica i Nikole Ristica
      </p>
    </div>
    <!--
      RECI AKO HOCES NESTO IZMENJENO!
      HVALA :D
      -->
  </div>
</template>

<script>
  import Header from './../components/layout/Header.vue'

  export default {
    name: 'about',
    components: {
      Header
     }
   }
</script>

<style>
 #tekst
  {
    margin-top: 1%;
    margin-left: 19vw;
    margin-right: 19vw;
    padding: 7vh;
    width: 90vh;
    background-color: rgba(169, 169, 169, 0.4);
    border-radius: 25px;
  }
</style>