<template>
    <div class="backdrop">
        <div class="modal" :class="{sale : theme === 'sale'}">
            <h1>{{  header }}</h1>
            <p>{{ description }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['header', 'description', 'theme'],
}
</script>

<style>
.modal{
    width: 400px;
    padding: 20px;
    margin: 10px auto;
    background: #fff;
    border-radius: 10px;
}

.modal.sale{
    background: crimson;
    color: #fff;
}

.modal.sale h1{
    color: #fff;
}

.backdrop{
    top: 0;
    position: fixed;
    background: #222;
    width: 100%;
    height: 100%;
}

.modal p{
    font-size: large;
}

.modal h1{
    color: rgb(67, 183, 183);
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 6px;
    font: 2em sans-serif;
    font-weight: 700;
}
</style>