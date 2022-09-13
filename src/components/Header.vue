<template>
    <header>
        <h1>{{ title }}</h1>
        <Button text="Add Task" color="green"></Button>
        <Button text="Update Task" color="blue"></Button>
        <Button text="Delete Task" color="red"></Button>
    </header>
</template>



<script>
import Button from './Button.vue'


export default {
    name: 'Header',
    components: {
        Button
    },
    props: {
        title: {
            type: String,
            default: "Hello World"
        }
    }
}
</script>



<!-- scoped means only this component gets this stylesheet -->
<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>