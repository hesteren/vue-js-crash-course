<template>
    <header>
        <h1>{{ title }}</h1>
        <Button v-show="homePage" @btn-click="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red' : 'green'"></Button>
        <!-- <Button text="Update Task" color="blue"></Button>
        <Button text="Delete Task" color="red"></Button> -->
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
        },
        showAddTask: Boolean
    },
    computed: {
        homePage() {
            if(this.$route.path === '/') {
                return true;
            } else {
                return false;
            }
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