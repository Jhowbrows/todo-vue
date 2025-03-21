<script setup>
    const props = defineProps(['tarefas']);
</script>

<template>
    <ul class="list-group mt-4">
        <li v-if="props.tarefas.length === 0" class="list-group-item text-center">
            Sem tarefas Pendentes
        </li>
      <li class="list-group-item" v-for="tarefa in props.tarefas">
        <input @change="evento => tarefa.finalizada = evento.target.checked" :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
        <label :for="tarefa.titulo" :class="{done: tarefa.finalizada}" class="ms-3">
          {{ tarefa.titulo }}
        </label>
      </li>
    </ul>
</template>

<style scoped>
  .done {
    text-decoration: line-through;
  }
</style>