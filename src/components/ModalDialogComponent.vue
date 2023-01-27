<template>
  <transition name="modal">
    <div class="modal-mask">
        <div class="modal-wrapper">
            <div class="modal-container">
                <slot name="header">
                    default header
                </slot>
            </div>
            <div class="modal-body">
                <slot name="body">
                    default body
                </slot>
            </div>
            <div class="modal-footer">
                <slot name="footer">
                    default footer
                    <button
                        class="modal-default-button"
                        @click="$emit('close')">
                        Ok
                    </button>
                </slot>
            </div>
        </div>
    </div>
  </transition>
</template>

<script>
export default {
    name: 'ModalDialogComponent',
}
</script>

<style scoped>

.modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
}

</style>