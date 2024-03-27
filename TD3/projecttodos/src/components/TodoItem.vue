<script>

export default {
    props: {
        todo: Object
    },
    methods: {
        remove : function() {
            this.$emit('remove', {id:this.todo.id});
        }
    },
    emits: ['remove']
}
</script>

<template>
    <li>
        <div class="checkbox" v-bind:class="{ 'alert alert-success': todo.checked}">
            <input type="checkbox" v-model="todo.checked"></input>
            {{ todo.text }}
            <button @click = remove()>Supprimer</button>
        </div>
    </li>
</template>