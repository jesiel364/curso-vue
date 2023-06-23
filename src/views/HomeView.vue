<script>

export default{
	computed: {
		ultimoPaciente() {
		let key = this.pacientes.length - 1
		let txt = ""
		
		txt += "Paciente " + this.pacientes[key].nome
		txt += ", Plano " + this.pacientes[key].plano
		return txt
		},
		
		pacientesOuro(){
			return this.pacientes.filter(item => item.plano == "Ouro")
		},
	},
	data(){
		return {
			pacientes: [],
		}
	},
	
	methods: {
		cadastrarPaciente(){
			this.pacientes.push({
				nome: nome.value,
				plano: plano.value,
			})
		}
	},
}
</script>

<template>
<h1>Adicionar Pacientes</h1>
<label for="nome">Nome</label>
<input id="nome" v-model="nome"><br>
<label for="plano">plano</label>
<input id="plano" v-model="plano"><br>
<button @click="cadastrarPaciente()">Cadastrar</button><br>

<hr>

<h2>Último paciente cadastrado</h2>
<p v-if="pacientes.length > 0">{{ ultimoPaciente }}</p>
<hr>

<h2>Pacientes plano ouro</h2>
<div v-if="pacientes" v-for="user in pacientesOuro">
	<p>{{ user.nome }}</p>
</div>
<hr>

<h2>Pacientes</h2>
<div v-for="user in pacientes">
	<p>{{user.nome}}, {{user.plano}}</p>
</div>


</template>
