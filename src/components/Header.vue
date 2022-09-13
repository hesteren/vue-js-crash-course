<template>
    <header>
        <h1>Task Tracker</h1>
    </header>
</template>



<script>
export default {
    name: 'Header'
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