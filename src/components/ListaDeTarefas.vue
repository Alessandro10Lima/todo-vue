<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <ul v-if="tarefas.length > 0" class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input class="checar" @change="evento => tarefa.finalizada = evento.target.checked " :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
            <label id="pre-tarefa" :class="{done: tarefa.finalizada}" class="ms-3" :for="tarefa.titulo">
            {{tarefa.titulo}}
            </label>
        </li>
    </ul>
    <p class="mt-3 fw-bold" v-else>Não existe tarefas pendentes</p>
</template>

<style scoped>
.done{
    text-decoration: line-through;
}

.checar{
    cursor: pointer;
}

#pre-tarefa{
    cursor: pointer;
}
</style>