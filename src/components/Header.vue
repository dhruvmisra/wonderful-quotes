<template>
    <div class="container">
        <h2>Quotes Added</h2>
        <div class="progress">
            <div class="progress-bar" :style="{width: (length/max*100) + '%'}">{{ length }}/{{ max }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['length', 'max']
    }
</script>

<style>
</style>
