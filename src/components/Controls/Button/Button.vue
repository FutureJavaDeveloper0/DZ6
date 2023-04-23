<script setup>
import { computed, ref } from "vue";
import css from "./Button.module.css";

const isScale = ref(false);
const props = defineProps(["styleType"]);
const classNames = computed(() => ({
    [css.btn_icon]: props.styleType === "icon",
    [css.btn_default]: !props.styleType,
}));
</script>

<template>
    <button :class="[classNames, css.btn]">
        <slot>
            

    
        </slot>
    </button>
</template>



<style >
.v-enter-active, 
.v-leave-active{
    transition: opacity 500ms ease;
}

.v-enter-from,
.v-leave-to{
    opacity: 0;
}
</style>