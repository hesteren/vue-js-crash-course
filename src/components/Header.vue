<template>
    <header>
        <h1>{{ title }}</h1>
    </header>
</template>



<script>
export default {
    name: 'Header',
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