<template>
    <div @click.self="closeModal()" class="backdrop">
        <div class="modal" :class="{sale: theme === 'sale'}">
            <!-- <h1 class="text-2xl text-slate-600 font-bold">{{ header }}</h1>
            <p>{{text}}</p> -->
            <!-- ? Slot is used to make a dynamical model layout it also can be used as named slot -->
            <slot>
                <h1 class="text-lg font-bold">This is default content of this modal</h1>
                <p>there is no data passed through </p>
            </slot>
            <div class="actions">
                <slot name="links">
                </slot>
            </div>
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

.modal .actions a {
    color: #333;
    border: 1px solid black;
    padding: 10px;
    border-radius: 10px;
}


.modal.sale .actions a{
    border: 1px solid #fff;
    color: #fff;
}

.modal.sale {
    background: green;
    color: white;
}

.modal.sale h1{
    color: white;
}
</style>