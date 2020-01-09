<template>
  <div class="header">
      <img src="../..assets/logo-patkica.png" />
      <router-link to="/"><button>Početna</button></router-link>
      <router-link to="/about"><button>Info</button></router-link>
    </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped>
 .header {
        height: 10vh; width: 100%;
        margin: 0;
        box-sizing: border-box;
        background-color: rgba(169, 169, 169, 0.4);
        display: grid;
        grid-template-columns: 10vw 10vw 10vw 20vw 20vw;
        justify-content: space-evenly;
        align-content: center;
    }
    .header button {
        padding: 1vh;
        border: none; border-radius: 1vh;
        background-color: rgb(230, 154, 13);
        font-weight: bold;
        font-size: 3vh
    }

    .header button:hover {
        background: darkgray;
    }

    .header img {
        height: 6vh;
        margin: 0;
    }

    @media only screen and (max-width: 600px){
        .header {padding: 3vh 0 0 5vw;};
    }

    @media (orientation: landscape) {
        .header {
            grid-template-columns: 10vw 15vw 15vw 5vw 5vw;
        }
    }
</style>