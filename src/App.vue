<template>
  <div id="app">
    <Encabezado>GIMNASIO</Encabezado>

    <form-task @new-task='newTask'></form-task>
    Cantidad de Tareas:{{cantidadTareas}}
    <List :tareas='listaTareas' @eliminar='deleteTask'></List>

    <pie-pagina></pie-pagina>
  </div>
</template>

<script>
import './assets/bootstrap.min.css';
import Encabezado from './components/Encabezado';
import PiePagina from './components/PiePagina';
import FormTask from './components/FormTask';
import List from './components/List';

export default {
  name: 'App',
  components: {
    Encabezado,
    FormTask,
    List,
    PiePagina
  },
  data (){
    return {
      listaTareas:[],
      cantidadTareas:0,
    }
  },
    methods:{
    newTask(task){
      if(this.task == '') return false;
      this.listaTareas.push (task);
    },
    deleteTask(key){
      this.listaTareas.splice(key,1);
    }
  },
  watch: {
    listaTareas(valor){
      this.cantidadTareas = valor.length

    }
  },
}

</script>

<style>
  body{
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    background-color:#003049;
    text-align:center;
    color: blanchedalmond;
  }
</style>
