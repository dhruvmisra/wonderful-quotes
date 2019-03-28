<template>
    <div class="card col-sm-12 col-md-6 col-lg-4">
        <div class="card-body">
            <slot></slot>
        </div>
    </div>

</template>

<script>
    export default {

    }
</script>

<style scoped>
.card{
    cursor: pointer;
    font-family: 'Pacifico', cursive;
    font-size: 22px;
}
.card:hover {
    background-color: rgb(255, 75, 75);
    color: white;
}
</style>
