<template>

<AddTask v-show="showAddTask" @add-task="addTask"></AddTask>
<Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"></Tasks>


</template>
  
<script>
    import Tasks from '../components/Tasks.vue'
    import AddTask from '../components/AddTask.vue'



  export default {
    name: 'Home',
    components: {
        AddTask,
        Tasks
    },
    props: {
        showAddTask: Boolean
    },
    created() {
        this.tasks = [
        {
            id: 1,
            text: 'School',
            day: 'March 1st at 2:30pm',
            reminder: true
        },
        {
            id: 2,
            text: 'Lunch',
            day: 'March 2nd at 2:30pm',
            reminder: true
        },
        {
            id: 3,
            text: 'Cinema',
            day: 'March 3rd at 2:30pm',
            reminder: false
        }
        ]
    },
    methods: {
        deleteTask(id) {
            if (confirm(`Are you sure you want to delete task: ${id}?`))
            this.tasks = this.tasks.filter((task) => task.id !== id);
        },
        toggleReminder(id) {
            this.tasks = this.tasks.map((task) => task.id == id ? {...task, reminder: !task.reminder } : task )
        },
        addTask(task) {
            this.tasks = [...this.tasks, task]
        }
    },
    data() {
        return {
            tasks: []
        }
    },
    inheritAttrs: false, // disable 'non-props' warning
  };
</script>