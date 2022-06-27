<template>
    <div class='loader'></div>
</template>

<style scoped>
.loader {
  border: 10px solid white; 
  border-top: 10px solid blueviolet; 
  border-radius: 50%;
  width: 100px;
  height: 100px;
  animation: spin 2s linear infinite;
}
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
@media screen and (max-width: 768px){
  .loader{
  width: 75px;
  height: 75px;
  }
}
</style>
    
