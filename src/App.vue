<template>
  <div id="app">
    <HelloWorld :msg="message"/>
    <!-- <h1>{{message}}</h1>
    <input v-model="angka1">
    <input v-model="angka2"><Button v-on:click="tambah()">tambah</Button> -->
    <div class="kalkulator">
      <hr>
		<h2 class="judul">BASIC KALKULATOR</h2>		
    <hr><br><br>	
			<input type="number" class="bil" v-model="angka1" placeholder="Masukkan Angka Pertama">
			<input type="number" class="bil" v-model="angka2" placeholder="Masukkan Angka Kedua">
      <br><br>
			<Button class="tombol" v-on:click="tambah()">+</Button> <Button class="tombol" v-on:click="kurang()">-</Button> <Button class="tombol" v-on:click="kali()">x</Button> <Button class="tombol" v-on:click="bagi()">/</Button> <Button class="tombol" v-on:click="mod()">%</Button>		
      <br><br>
      <h3 class="jawaban">{{hasil}}</h3>
      <br><br>
      <p align="center" text-color="#ffffff">Andri Setya Hermawan</p>													
	</div>
  <br>
  <div class="kalkulator">
      <hr>
		<h2 class="judul">TRIGONOMETRY KALKULATOR</h2>		
    <hr><br><br>	
			<input type="number" class="bil" v-model="angkaTrigono" placeholder="Masukkan Angka">
      <br><br>
			<Button class="tombol" v-on:click="sin()">Sin</Button> <Button class="tombol" v-on:click="cos()">Cos</Button> <Button class="tombol" v-on:click="tan()">Tan</Button>  		
      <br><br>
      <h3 class="jawaban">{{hasilTrigono}}</h3>
      <br><br>
      <p align="center" text-color="#ffffff">Andri Setya Hermawan</p>													
	</div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data(){
    return{
      hasil : 0,
      angka1 : 0,
      angka2 : 0,
      angkaTrigono : 0,
      hasilTrigono : 0
    }
  },
  methods:{
    tambah(){
      this.hasil = parseInt(this.angka1) + parseInt(this.angka2);
    },
    kurang(){
      this.hasil = parseInt(this.angka1) - parseInt(this.angka2);
    },
    kali(){
      this.hasil = parseInt(this.angka1) * parseInt(this.angka2);
    },
    bagi(){
      this.hasil = parseInt(this.angka1) / parseInt(this.angka2);
    },
    mod(){
      this.hasil = parseInt(this.angka1) % parseInt(this.angka2);
    },
    sin(){
      this.hasilTrigono = Math.sin(parseInt(this.angkaTrigono));
    },
    cos(){
      this.hasilTrigono = Math.cos(parseInt(this.angkaTrigono));
    },
    tan(){
      this.hasilTrigono = Math.tan(parseInt(this.angkaTrigono));
    },
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  background: #a5d7f0;
}

.kalkulator{
	width: 335px;
	background: rgb(90, 47, 47);
	margin: 100px auto;
	padding: 10px 20px 50px 20px;
	border-radius: 5px;
	box-shadow: 0px 10px 20px 0px #D1D1D1;
}
 
.bil{
	width: 300px;
	margin: 5px;
	border: none;
	font-size: 16pt;
	border-radius: 5px;
	padding: 10px;	
}

.jawaban{
  width: 300px;
	margin: 5px;
	border: none;
	font-size: 16pt;
	border-radius: 5px;
	padding: 10px;	
  background: #a5d7f0;
}
 
.tombol{
	background: #EC5159;
	border-top: none;
	border-right: none;
	border-left: none;
	border-radius: 5px;
	padding: 10px 20px;
	color: #eee;
	font-size: 15pt;
	border-bottom:4px solid #BF3D3D;
}
 
.judul{
	text-align: center;
	color: #eee;
	font-weight: normal;
}
</style>
