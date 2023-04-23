
<script setup>
import { computed, ref } from "vue";
import Checkbox from "../Controls/Checkbox/Checkbox.vue";
import css from "../Letter/Letter.module.css";

const { date } = defineProps(["date", "senderMail", "important"]);

const stringDate = computed(() => {
    return Intl.DateTimeFormat("ru-RU",
        {
            month: "short", day: "numeric",
            hour: "numeric", minute: "numeric"
        })
        .format((date));
});
</script>

<template>
    <!-- <div :class="css.letter">
            <div name="important" class="important">
                <Checkbox />
                <span v-if="important">!</span>
            </div>
            <div class=""><slot name="sender"></slot></div>
            <div class=""><slot name="title"></slot></div>
            <div class="" name="date">{{ stringDate }}</div>
        </div> -->
    
    <div class = "container">
            
                

                <table class = "table table-striped">
                    <thead>
                        <tr>
                            <th> Is important? </th>
                            <th> Sender </th>
                            <th> Message </th>
                            <th> Data </th>
                        </tr>

                    </thead>
                    <tbody >
                        <td :class="css.table">
                            <div  name="important" class="important">
                                <!-- <Checkbox /> -->
                                <span v-if="important">Yes.</span>
                                <span v-else>No.</span>
                            </div>
                        </td>
                        <td :class="css.table">
                            <div class=""><slot name="sender"></slot></div>
                        </td>
                        <td :class="css.table">
                            <div class=""><slot name="title"></slot></div>
                        </td>
                        <td :class="css.table">
                            <div class="" name="date">{{ stringDate }}</div>
                        </td>
                    </tbody>
                </table>
            </div>
    <!-- <div :class="css.letter">
        <div name="important" class="important">
            <Checkbox />
            <span v-if="important">!</span>
        </div>
        <div class=""><slot name="sender"></slot></div>
        <div class=""><slot name="title"></slot></div>
        <div class="" name="date">{{ stringDate }}</div>
    </div> -->
    
</template>



