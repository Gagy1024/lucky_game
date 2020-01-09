<template>
  <div class="about" style="{'background-image':'url(../assets/background.png)'}">
    <!--<Header />-->
    <h1>INFO</h1>
    <div id="levi"><img id="logo" src="../assets/logo-patkica.png"><p>LUCKY GAME</p></div>
    <div id="desni">
      <p>Nesto o aplikaciji....</p><br/>
      <p>Pravila:<br/>...pravila??...</p>
      <p id="tim">WebApp "Lucky Game" jer razvijena od strane Dragana Todorovica, Nenada Sarovica i Nikole Ristica</p>
    </div>
    <!--
      RECI AKO HOCES NESTO IZMENJENO!
      HVALA :D
      -->
  </div>
</template>

<script>
  //import Header from '../components/layout/Header.vue'

  //export default {
    //name: 'Header',
    //components: {
      //Header
    //}
  //0}
</script>

<style>
  #tim
    {
      color: gray;
    }
  #levi
    {
      float: left;
      border-radius: 30px;
      background: white;
      padding: 2%;
      border: 3px solid green;
    }
  #logo
    {
      width: 17vw;
      height: 17vw;
      text-align: center;
    }
  #desni
    {
      text-align: center;
      float: left;
      border-radius: 30px;
      background: white;
      width: 60%;
      padding: 5%;
      margin-left: 7px;
      border: 3px solid green;
    }
</style>