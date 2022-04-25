<template>
    <header>
        <h1>{{ title}}</h1>
        <ButtonItem 
        @btn-click="$emit('toggle-add-task')" 
        :text="showAddTask ? 'Close' : 'Add Task'" 
        :color="showAddTask ? 'red' : '#66CD00'" />
    </header>
</template>

<script>
import ButtonItem from "./ButtonItem"

export default {
    name: "HeaderItem",
    props: {
        title: String,
        showAddTask: Boolean
    },
    components: { ButtonItem }
}
</script>

<style scoped>
header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 20px;
    color: #3b3b3b;
}
</style>