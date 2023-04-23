<script setup>
import { Transition } from "vue";
import css from "./Header.module.css";
import Input from "../Controls/Input/Input.vue";
import Button from "../Controls/Button/Button.vue";
</script>

<template>
    <header>
        <ul :class="css.header">
            <li :class="css.header__logo">MyMail</li>
            <li :class="css.header__search">
                <Input placeholder="Поиск сообщений" styleType="main" />
            </li>
            <li :class="css.header__help">
                <Transition>
                    <Button styleType="icon"><img  src="/help.svg"  
                     alt="help" width="35" height="35"></Button>
                </Transition> 
            </li>
        </ul>
    </header>
</template>

<style scoped>
.v-enter-active, 
.v-leave-active{
    transition: opacity 500ms ease;
}

.v-enter-from,
.v-leave-to{
    opacity: 0;
}
</style>
