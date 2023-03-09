<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale' }">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['header', 'text', 'theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>


<style>
.backdrop {
    position: fixed;
    top: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
}

.modal {
    width: 400px;
    padding: 20px;
    border-radius: 10px;
    margin: 100px auto;
    background: #fff;
}

.modal.sale {
    background: crimson;
    color: white;
}
</style>