<script>
    export default {
        name: 'ProjCard',
        props: {
            project: Object
        }
    }
</script>

<template>
    <div class="card">
        <div class="card-body text-center bg-dark text-white">
            <h6>{{ project.title }}</h6>
            <p><strong>ID: </strong>{{ project.id }}</p>
            <p><strong>TYPE: </strong>{{ project.type }}</p>
            <p><strong>CONTENT: </strong>{{ project.content }}</p>
        </div>
    </div>
</template>

<style scoped lang="scss">
    .card-body {
        border-radius: 8px;
        height: 375px;
    }
</style>