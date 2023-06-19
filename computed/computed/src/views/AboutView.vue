<template>
  <div class="about">
    <h1>Consulta</h1>
   <p> {{paciente}}</p>
    <input placeholder="Nome" v-model="paciente"><br>
    
    <input type="radio" value="m" v-model="sexo">Masculino
    <input type="radio" value="f" v-model="sexo">Feminino
    <p>{{sexo}}</p>
    
    <input v-model="doencas" type="checkbox" value="100">Asma
    <input v-model="doencas" type="checkbox" value="101">Diabetes 2
    <input v-model="doencas" type="checkbox" value="102">Gripe
    
    <p>{{doencas}}</p>
    
    <select v-model="plano">
    	<option value="1">Básico 1</option>
    	<option value="2">Básico 2</option>
    	<option value="3">Master</option>
    </select>
    
    <p>{{plano}}</p>
    
    <textarea v-model="diagnóstico" placeholder ="diagnóstico"/>
    
    <p>{{diagnóstico}}</p>
    
    
  </div>
</template>
<script>

export default{
	data(){
		return {
			paciente: "",
			sexo: "",
			doencas: [],
			plano: "",
			diagnóstico: ""
		}
	},
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
