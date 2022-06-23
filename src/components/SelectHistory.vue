<template>
    <div>{{printHistory}}</div>
</template>

<script>

export default {
    props:['lastFiveHistory'],
    computed:{
        printHistory(){
            console.log('lastFiveHistory',this.lastFiveHistory)
            return this.lastFiveHistory;
        }
    }
}
</script>

<style scoped>

</style>
