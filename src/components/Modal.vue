<script setup lang="ts">
defineEmits<{
    (e: 'close'): void,
}>()
</script>

<template>
    <div class="modal">
        <div class="close">
            <button @click="$emit('close')">Close</button>
        </div>
        <slot></slot>
    </div>
    <div class="overlay"></div>
</template>

<style lang="scss" scoped>
.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: black;
    opacity: 0.5;
    z-index: 999;
}

.modal {
    position: fixed;
    display: flex;
    flex-direction: column;
    // top: 50%;
    left: 50%;
    transform: translate(-50%, 50%);

    width: 900px;
    max-height: 800px;
    background: var(--hl-bg);
    z-index: 1000;
    padding: 20px;

    .close {
        text-align: right;
    }
}
</style>