<template>
    <button class="clear-buttton">{{buttonTitle}}</button>
</template>

<script>

export default {
    props: ['buttonTitle']
}
</script>

<style scoped>
.clear-buttton{
    display: block;
    width: 15%;
    background-color: rgb(93, 7, 173);
    color: white;
    text-align: center;
    font-size: 15px;
    margin: 15px auto;
    padding: 10px;
    border-radius: 10px;
    border: none;
}
.clear-buttton:hover{
    background-color: rgb(133, 82, 180);
    color: black;
}
</style>
