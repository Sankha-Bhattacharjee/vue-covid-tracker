<template>
    <select v-model="selected" class="country-dropdown">
        <option value="0" selected disabled>Select Country</option>
    </select>
</template>

<script>

export default {
    props: ['countries'],
    data(){
        return {
            selected: '',
        }
    }
}
</script>

<style scoped>
.country-dropdown{
    width: 50%;
    text-align: center;
    display: block;
    margin: 10px auto;
}
</style>
