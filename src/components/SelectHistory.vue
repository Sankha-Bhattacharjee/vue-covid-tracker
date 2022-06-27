<template>
    <div class="history-container">
        <span class="history-label"><em>Recent Searches</em></span>
        <span v-for="history in historyList" :key="history" class="history slide-left">{{history}}</span>
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
.slide-left {
	-webkit-animation: slide-left 0.5s linear forwards;
	        animation: slide-left 0.5s linear forwards;   
}
@keyframes slide-left {
  0% {
    -webkit-transform: translateX(10px);
            transform: translateX(10px);
            opacity: 0;
  }
  100% {
    -webkit-transform: translateX(0px);
            transform: translateX(0px);
            opacity: 1;
  }
}
@media only screen and (max-width: 768px) and (min-width: 481px) {
.history-container{
    grid-template-columns: auto auto auto auto;
}
.history-label{
    grid-row: 1/span 2;
}
}
@media only screen and (max-width: 480px){
.history-container{
    grid-template-columns: auto auto;
}
.history-label{
    font-size: 0.9em;
    grid-column: 1 / span 2;
}
.history{
    font-size: 0.9em;
}
}
</style>
