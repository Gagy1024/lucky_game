<template>
  <div class="about">
    <Header />
    <div id="tekst">
      <p>
      LUCKY GAME<br/>
      Devloped by: <br/>
      <b>Dragan Todorovic</b><br/>
      <b>Nenad Sarovic</b><br/>
      <b>Nikola Ristic</b><br/>
      </p>
    </div>
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