<template>
	<ul class="list-group">	
		<li class="list-group-item" v-bind:class="{terminada: tarea.terminada}" v-for="(tarea,indice) in tareas">	
			{{ tarea.texto }}
			<span class="pull-right">
			<button type="button" class="btn btn-success btn-xs glyphicon glyphicon-ok" v-on:click="tarea.terminada = !tarea.terminada">
			</button>
			<button type="button" class="btn btn-danger btn-xs glyphicon glyphicon-remove" v-on:click="borrarTarea(indice)">
			</button>
			</span>
		</li>
	</ul>
</template>

<script> 
export default {
	props:['tareas'],
	methods: {
		borrarTarea(indice){
			this.tareas.splice(indice,1);
		}
	}
}	
</script>

<style scoped>
	.terminada{
		color: gray;
		text-decoration: line-through;
	}
</style>