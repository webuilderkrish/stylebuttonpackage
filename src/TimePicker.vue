<template >

<div v-click-outside="hideDialog">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
    <div>
    <input type="input" class="form-control" :value=" this.time.hours + ' : ' +  this.time.minutes" readonly v-on:click="openDialog">
    </div>
    <div v-if="displayMinutes" >
    <select class="form-control btn-group" v-model="time.hours"  v-on:change="hoursChanged($event.target.value)">
        <option v-for="n in hour" :key="n" :value="n" > 
            {{ n }} 
        </option>
    </select>
  
    <select class="form-control btn-group" v-model="time.minutes"  v-on:change="minutesChanged($event.target.value)">
        <option v-for="n in this.mins" :key="n" :value="n">
           {{n}}
        </option>
    </select>
    </div>

</div>
</template>
<script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>

<script src="./TimePicker.js"></script>
<style scoped>
    .btn{
        border: 1px solid gray;
    }
    #colon{
        margin-top: 10px;      
        margin-left: 10px;
        font-size: 40px
    }
    input{
        padding-left: 15px;
        width: 88px;
    }
    select{
        width: 43px;
        padding: 1px
    }
</style>