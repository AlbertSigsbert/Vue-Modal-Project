<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale' }">
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

.modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
    color: #333;
}

.modal .actions a {
    padding: 8px;
    color: #333;
    border: 1px solid #eee;
    border-radius: 4px;
    margin: 10px;
    text-decoration: none;
}

.modal.sale {
    background: crimson;
    color: white;
}
</style>