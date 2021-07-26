<template>
    <div>
        <h1>Income and Expense Account</h1>
        <form action="#" @submit="insertData">
        <div class="input">
            <div class="catagory">
                <label for="catagory">Catagory: </label>
                <select v-model="data.category" required>
                    <option value="income">Income</option>
                    <option value="expense">Expense</option>
                </select>
            </div>
            <div class="date">
                <label for="date">Date: </label>
                <input type="date" v-model="data.date" required>
            </div>
            <div class="amount">
                <label for="amount">Amount: </label>
                <input type="number" v-model="data.amount" required>
            </div>
            <div class="note">
                <label for="note">Note: </label>
                <input type="text" v-model="data.note" placeholder="Insert a note">
            </div>
            <button type="submit">Confirm</button>
        </div>
        </form>
    </div>
</template>

<script>
export default {
    data(){
        return {
            data : {
                category:'income',
                date:null,
                note:'',
                amount:0
            }
        }
    },
    methods:{
        insertData(e){
            this.$store.commit('insertData',this.data)
            e.preventDefault()
        }
    }
}
</script>

<style lang = "css" scoped>
.input{
    padding: 25px;
    background-color: rgba(255, 203, 107, 0.808);
}
.date, .amount, .note, .type{
    padding: 10px;
}

h1{
    padding: 0px 0px 10px 0px;
    font-size: 4ex;
}
</style>