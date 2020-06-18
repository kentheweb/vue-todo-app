<template>
<div class="container">
    <br>
    <h4>binding to classes</h4>
    <label for="name">enter your name : </label> {{message}}
    <br>
    <input type="text" v-model="message" :class="{red : message.length < 5}" class="form-control  form-control-sm">
    <br>
    <br>
    <h4>rendering html tags</h4>
    <textarea v-model="htm" cols="30" rows="5" class="form-control form-control-sm">
    </textarea>
    <!-- rendering html -->

    <div v-html="htm">
        
    </div>
    <!-- for loop using vue -->
    <h4>the for loop</h4>
    <br>
    <input type="text" placeholder="add item" class="form-control form-control-sm" v-model="item" required @keypress.enter="AddItem">
    <br>
    <button @click="AddItem" class="btn btn-danger">+ add</button>
    <ul>
        <li v-for="(cats, index) in cats" :key="index">
            <a href="" class="text-decoration-none">{{index}} .  {{cats}}</a>
        </li>
    </ul>
    <button class="btn btn-success" @click="Remove">- remove</button>
</div>
</template>

<script>
export default {
    data(){
        return{
            message: '',
            htm: '',
            cats: [
                'dog',
                'marry',
                'john',
                'brenda'
            ],
            item: ''
        }
    },
    methods:{
        AddItem(){
            this.cats.push(this.item)
            this.item = ''
        },
        Remove(){
            this.cats.splice(this.cats.length - 1, 1)
        }
    }    
}
</script>

<style scoped>
.red{
    border: 1px solid red;
}
li{
    list-style: none;
}
</style>>

