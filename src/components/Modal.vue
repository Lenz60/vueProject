<template>
    <div @click.self="closeModal()" class="backdrop">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <h1 @click="checkModal()" class="text-2xl text-slate-600 font-bold">{{ header }}</h1>
            <p>{{text}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['header','text', 'theme'],
    methods: {
        closeModal(){
            this.$emit('close')
        }
    }
}
</script>

<style>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
    text-align: center;
}
.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}

.modal.sale {
    background: green;
    color: white;
}

.modal.sale h1{
    color: white;
}
</style>