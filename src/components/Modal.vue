<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale : theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>

    <div class="backdrop" @click.self="closeModalTwo">
        <div class="modal" :class="{sale : theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['theme'],
    methods: {
        closeModal(){
            this.$emit('close')
        },
        closeModalTwo(){    
            this.$emit('close')
        }
    }
}
</script>

<style>
.modal{
    width: 400px;
    padding: 20px;
    margin: 40px auto;
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
    padding-bottom: 2px;
    font: 2em sans-serif;
    font-weight: 700;
}

a{
    border: 1px solid #ddd;
    text-decoration: none;
    padding: 10px 16px;
    margin: 10px;
    color: black;
}
</style>