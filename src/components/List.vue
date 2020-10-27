<template>
    <div>
        <ul v-if='tareas.length !=0'>
            <li v-for='(tarea, key) in tareas' :key='key' @click='eliminar(key)'>
                {{tarea}}
            </li>
        </ul>
        <h3 v- else>
            No hay tareas pendientes
        </h3>
    </div>
</template>

<script>
export default {
    name:'List',
    props:{
        tareas: Array
    },
    methods:{
        eliminar(key){
            this.$emit('eliminar',key)
        }
    },
}
</script>

