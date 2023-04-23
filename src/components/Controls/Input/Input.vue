<script setup>
import { computed } from "vue";
import css from "./Input.module.css";

const props = defineProps(["styleType"]);
const classNames = computed(() => ({
    [css.input_main]: props.styleType === "main",
    [css.input_default]: !props.styleType,
}));
</script>


<template>
    <div :class="css.input__wrapper">
        <input :class="[classNames]" :placeholder="Поиск" type="text"/>
        <span :class="css.input__icon"><slot><img src="/search.svg" width="15" height="15"/></slot></span>
    </div>
    
</template>


