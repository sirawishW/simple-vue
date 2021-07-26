<template>
    <div>
        <table>
            <thead>
                <tr>
                    <td>#</td>
                    <td>Category</td>
                    <td>Date</td>
                    <td>Amount</td>
                    <td>Note</td>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(v,index) in fetchData" :key="index">
                    <td>{{ index + 1 }}</td>
                    <td>{{ v.category }}</td>
                    <td>{{ v.date }}</td>
                    <td>{{ v.amount }}</td>
                    <td>{{ v.note ? v.note : '-' }}</td>
                </tr>
            </tbody>
        </table>
        <h5>Income : {{ income }} Expense : {{ expense }} Total : {{ total }}</h5>
    </div>
</template>

<script>
export default {
    data(){
        return{
            income:0,
            expense:0,
            total:0
        }
    },
    computed:{
        fetchData(){
            this.calculated()
            return this.$store.state.data
        }
    },
    methods:{
        calculated(){
            const data = this.$store.state.data

            this.income = 0
            this.expense = 0
            this.total = 0
            
            data.forEach(element => {
                if(element.category == 'income'){
                    this.income += Number(element.amount)
                    this.total += Number(element.amount)
                }else{
                    this.expense += Number(element.amount)
                    this.total -= Number(element.amount)
                }
            });
        }
    }
}
</script>
<style lang = "css" scoped>
h5{
    font-size: 2.5ex;
}
td{
    border-bottom: 1px solid orange;
    font-size: 2ex;
}

</style>