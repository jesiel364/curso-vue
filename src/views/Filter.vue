<template>
	<input v-model="user">
	
	<p v-if="lista" v-for="p in lista">{{p.nome}}</p>
	<p v-else v-for="p in pacientes">{{p.nome}}</p>
	
	
</template>
<script>
	
	export default{
		data(){
			return{
				pacientes: [
					{nome: "João"},
					{nome: "Julho"},
					{nome: "Jean"},
					{nome: "Joaquim"},
				]
				,
				user: "",
				lista: ""
			}
		},
		watch:{
			user(valorNovo){
				this.lista = this.pacientes.filter(p => p.nome.match(this.user))
				 
			}
		}
	}
</script>