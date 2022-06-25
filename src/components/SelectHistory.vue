<template>
    <div class="history-container">
        <span class="history-label"><em>Recent Searches</em></span>
        <span v-for="history in historyList" :key="history" class="history">{{history}}</span>
    </div>
</template>

<script>

export default {
    props:['lastFiveHistory'],
    computed:{
        historyList(){
            console.log('lastFiveHistory',this.lastFiveHistory)
            return this.lastFiveHistory;
        }
    }
}
</script>

<style scoped>
.history-container{
    display: grid;
    grid-template-columns: auto auto auto auto auto auto;
    justify-content: left;
    align-items: center;   
    max-width: 50%;
    gap: 10px;
}
.history{
    display: block;
    border: 2px solid rgb(106, 0, 192);
    border-radius: 5px;
    padding: 5px;
    margin-top: 10px;
}
.history-label{
    font-size: 1.2em;
    color: rgb(95, 82, 82);
    padding: 3px;
}
</style>
