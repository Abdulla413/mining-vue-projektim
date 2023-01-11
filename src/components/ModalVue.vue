<script setup >

defineProps({
    show:Boolean
})




</script>

<template >
    <Transition
    enter-from-class="opacity-0 scale-125"
    enter-to-class="opacity-100 scale-100"
    enter-active-class="transition duration-500"
    leave-active-class="transition duration-300"
    leave-from-class="opacity-100 scale-100"
    leave-to-class="opacity-0 scale-125"
    >
    <div class="modal-mask" v-if="show">
        <div class="modal-container">
            <div>
            <slot>default body</slot>
            </div>
        <footer class="modal-footer">
            <slot name="footer">
                <button @click="$emit('close')">
                    Close
              </button>
            </slot>
        </footer>
        </div>
    </div>
</Transition>
</template>

<style>
.modal-mask {
position: fixed;
inset: 0;
background-color: rgba(0,0,0,.6);
display: grid;
place-items: center;

}

.modal-container {
    background-color: white;
    padding: 1rem;
    width: 75vw;
    max-width: 500px;
    border-radius: 20px;
}

.modal-footer{
    border-top: 1px solid #ddd;
    margin-top: 1rem;
    padding-top: 0.5rem;
    font-size:0.8rem;
}

.modal-footer button {
    background:#ddd;
    padding:.25rem .75rem;
    border-radius: 20px;
}
.modal-footer button:hover {
    background:rgb(176, 174, 174);
    
}

</style>