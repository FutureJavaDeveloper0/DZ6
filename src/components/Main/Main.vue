<script setup>
import Letter from "../Letter/Letter.vue";
import css from "../Main/Main.module.css";
</script>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            messages: [{}],
        };
    },
    mounted() {
        axios.get('http://localhost:8080/main/myMail')
            .then((response) => {
                this.messages = response.data;
            });
    },
};
</script>


<template>
  
    <main>
         <aside></aside>
         <section :class="css.letters">
            <Letter v-for="message in messages" 
            :title="message.title" 
            :important="message.important"
            :sender="message.sender"
            :senderMail="message.senderMail"
            :date="message.date" 
            > 
            <template #title> {{ message.title }}</template>
            <template #sender> {{ message.sender }}</template>
            <template #important> {{ message.important }}</template>
            <template #date> {{ message.date }}</template>
            </Letter>
         </section>
    </main>

</template>



<style lang="scss" scoped>

</style>