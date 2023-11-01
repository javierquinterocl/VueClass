<script setup>
import { ref } from "vue";

let notifications = ref(0)

function addValue(){
    notifications.value++
    console.log(notifications);
}
function minusValue(){
    if( notifications.value > 0){
        notifications.value--
    }
    
    console.log(notifications);
}


</script>

<template>
    <div class="wrapper">
        <div class="profile">
            <div class="notification" v-show="notifications > 0">{{ notifications }}</div>
        </div>
        <div class="button-wrapper">
            <button class="button" @click="minusValue">-</button>
            <button class="button" @click="addValue">+</button>
        </div>
        <div v-if="notifications ==0">
            I am hainsemberg 😎
        </div>
        <div v-else>
            I am the danger 😡
        </div>
    </div>

</template>

<style scoped>
.wrapper {
    background-color: #d9d9d9;
    width: 20%;
    border-radius: 8px;
    margin: 0 auto;
    padding-top: 32px;
    overflow: hidden;
}
.profile {
    background-color: purple;
    width: 120px;
    height: 120px;
    border-radius: 100%;
    margin: 0 auto;
    position: relative;
    background-image: url('https://upload.wikimedia.org/wikipedia/en/thumb/0/03/Walter_White_S5B.png/220px-Walter_White_S5B.png');
    background-size: cover;
}

.notification {
    display: flex;
    padding: 2px;
    position: absolute;
    background-color: red;
   min-width: 18px; 
    height: 18px;
    border-radius: 100%;
    align-items: center;
    justify-content: center;
    color: wheat;
    top: 0;
    right: 0;
}
.button-wrapper {
    text-align: center;
    margin-top: 12px;
    padding: 10px 0;
    outline: none;
}
.button {
    background-color: #e3371e;
    border-radius: 4px;
    padding: 2px 0;
    width: 40px;
    cursor: pointer;
    font-weight: bold;
    color: white;
    display: inline-block;
    outline:none;
    border: none;
}
.button:first-child {
    margin-right: 8px;
}
.button:last-child {
    margin-left: 8px;
}
button:active{
    outline: 0 none;
    border: none;
}
</style>
