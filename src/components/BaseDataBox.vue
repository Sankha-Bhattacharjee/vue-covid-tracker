<template>
    <div>
        <!-- Cases -->
        <h3>Cases</h3>
        <div>
            <span>New:</span>
            {{newConfirmCases}}
        </div>
        <div>
            <span>Total:</span>
            {{totalCases}}
        </div>
        <!-- Deaths -->
        <h3>Deaths</h3>
        <div>
            <span>New:</span>
            {{newConfirmDeathss}}
        </div>
        <div>
            <span>Total:</span>
            {{totalDeaths}}
        </div>
    </div>
</template>

<script>
export default {
    props: ['stats'],
    computed:{
        newConfirmCases(){
            return this.formatNumber(this.stats.NewConfirmed);
        },
        totalCases(){
            return this.formatNumber(this.stats.TotalConfirmed);
        },
        newConfirmDeaths(){
            return this.formatNumber(this.stats.NewDeaths);
        },
        totalDeaths(){
            return this.formatNumber(this.stats.TotalDeaths);
        }
    },
    methods:{
        formatNumber(num){
            return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g,',');
        }
    },

}
</script>
