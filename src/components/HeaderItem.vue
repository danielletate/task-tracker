<template>
    <header>
        <h1>{{ title}}</h1>
        <ButtonItem @toggle-add-task="$emit('toggle-add-task')" text="Add Task" color="#66CD00" />
    </header>
</template>

<script>
import ButtonItem from "./ButtonItem"

export default {
    name: "HeaderItem",
    props: {
        title: String,
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