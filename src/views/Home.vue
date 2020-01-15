<template>
<div class="home">
<Header />
<div id="pokreni" class="button"><div class="outer"><div class="height"><div class="inner"><router-link id="router" to="/Game">Pokreni igru</router-link></div></div></div></div>
  <router-view/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from './../components/layout/Header.vue'

export default {
  name: 'home',
  components: {
    Header
  }
}
</script>


<style>
.home {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}
#pokreni{
  display: inline-block;
  margin-left: auto;
  margin-right: auto;
}
#router{
    color:#000000;
  font-weight: bold;
  text-decoration: none;
}
#info{
  padding-right: -50px;
  display: inline-block;
  float: right;
}
body {
	font-family: Impact;
  background-image: url('../assets/background.png');
  background-size: 100%;
}
.button {
	height: 80px;
	width: 300px;
	cursor: pointer;
	margin: 50px auto;
}
.button .outer {
	position: relative;
	width: 100%;
	height: 100%;
	padding: 2px;
	background: rgba(0,0,0,0.65);
	border-radius: 14px;
	-webkit-border-radius: 14px;
	-moz-border-radius: 14px;
	box-shadow: inset rgba(0,0,0,0.85) 0px 1px 5px;
	-webkit-box-shadow: inset rgba(0,0,0,0.85) 0px 1px 5px;
	-moz-box-shadow: inset rgba(0,0,0,0.85) 0px 1px 5px;
	-webkit-transform: perspective(500px) rotateX(35deg);
	-moz-transform: perspective(500px) rotateX(35deg);
}
.button .outer .height {
	position: relative;
	height: 100%;
	margin-top: -15px;
	padding-bottom: 15px;
	background: #ff7d03;
	border-radius: 16px;
	-webkit-border-radius: 16px;
	-moz-border-radius: 16px;
	box-shadow: rgba(0,0,0,0.85) 0px 1px 1px, inset rgba(0,0,0,0.35) 0px -2px 8px;
	-webkit-box-shadow: rgba(0,0,0,0.85) 0px 1px 1px, inset rgba(0,0,0,0.35) 0px -2px 8px;
	-moz-box-shadow: rgba(0,0,0,0.85) 0px 1px 1px, inset rgba(0,0,0,0.35) 0px -2px 8px;
	-webkit-transition: all 0.1s ease-in-out;
	-moz-transition: all 0.1s ease-in-out;
}       
.button:hover .outer .height {
	margin-top: -10px;
	padding-bottom: 10px;
	background: #ff7d03;
	box-shadow: rgba(0,0,0,0.25) 0px 1px 1px, inset rgba(0,0,0,0.35) 0px -2px 6px;
	-webkit-box-shadow: rgba(0,0,0,0.25) 0px 1px 1px, inset rgba(0,0,0,0.35) 0px -2px 6px;
	-moz-box-shadow: rgba( 0,0,0,0.25) 0px 1px 1px, inset rgba(0,0,0,0.35) 0px -2px 6px;
}
.button:active .outer .height {
	margin-top: 0px;
	padding-bottom: 0px;
}
.button .outer .height .inner {
	line-height: 2.8em;
	font-size: 30px;
	letter-spacing: .05em;
	position: relative;
	height: 100%;
	text-align: center;
	text-shadow: #ff7d03 0px 0px 1px;
	background: #ff7d03;
	background: -moz-linear-gradient(top, #ff7d03 0%, #ff7d03 100%); /* FF3.6+ */
	background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#ff7d03), color-stop(100%,#ff7d03)); /* Chrome,Safari4+ */
	background: -webkit-linear-gradient(top, #ff7d03 0%,#ff7d03 100%); /* Chrome10+,Safari5.1+ */
	background: linear-gradient(top, #ff7d03 0%,#ff7d03 100%); /* W3C */
	border-radius: 12px;
	-webkit-border-radius: 12px;
	-moz-border-radius: 12px;
	box-shadow: inset rgba(255,255,255,0.85) 0px 0px 1px;
	-webkit-box-shadow: inset rgba(255,255,255,0.85) 0px 0px 1px;
	-moz-box-shadow: inset rgba(255,255,255,0.85) 0px 0px 1px;
	-webkit-transition: all 0.1s ease-in-out;
	-moz-transition: all 0.1s ease-in-out;
}
.button:hover .outer .height .inner{
	text-shadow: #ff7d03 0px 0px 1px;
	background: #d1ddd0; /* Old browsers */
	background: -moz-linear-gradient(top, #ff7d03 0%, #ff7d03 100%); /* FF3.6+ */
	background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#43d034), color-stop(100%,#ff7d03)); /* Chrome,Safari4+ */
	background: -webkit-linear-gradient(top, #ff7d03 0%,#ff7d03 100%); /* Chrome10+,Safari5.1+ */
	background: linear-gradient(top, #ff7d03 0%,#ff7d03 100%); /* W3C */
}
.button:active .outer .height .inner{
	text-shadow: #319926 0px 1px 0px;
	border-radius: 16px;
	-webkit-border-radius: 16px;
	-moz-border-radius: 16px;
	box-shadow: inset rgba(0,0,0,0.9) 0px 0px 8px;
	-webkit-box-shadow: inset rgba(0,0,0,0.9) 0px 0px 8px;
	-moz-box-shadow: inset rgba(0,0,0,0.9) 0px 0px 8px;
	background: orange;
	background: -moz-linear-gradient(top, #ffbb00 0%, #ffbb00 100%); /* FF3.6+ */
	background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#ffbb00), color-stop(100%,#ffbb00)); /* Chrome,Safari4+ */
	background: -webkit-linear-gradient(top, #ffbb00 0%,#ffbb00 100%); /* Chrome10+,Safari5.1+ */
	background: linear-gradient(top, #ffbb00 0%,#ffbb00 100%); /* W3C */
}
#loptice{
    height: 150px;
    width: 150px;
    background-image: url('../assets/lopticaaa.png');
    border-radius: 50%;
    display: inline-block;
    margin-right: 5px;
    text-align: center;
    font-size: 50px;
    font-style: bold;
    align-content: center;
    vertical-align: bottom;
	animation: pulse 1s infinite ease-in-out alternate;
    }
#broj2{
    margin-top: 45px;
    }
#glavnibroj{
    margin-top: 70px;
	}
#glavnaloptica{
	font-size: 140px;
	text-decoration-color: aliceblue;
    font-style: bold;
	display: inline-block;
	align-content: center;
	background-image: url('../assets/glavnaloptica.png');
	animation: grow 5s ease infinite;
    width: 300px; height: 300px;
}
@keyframes grow {
  from {
    transform: scale(0);
  }
  to {
    transform: scale(1);
  }
}
@keyframes pulse {
  from { transform: scale(0.8); }
  to { transform: scale(1.2); }
}
</style>