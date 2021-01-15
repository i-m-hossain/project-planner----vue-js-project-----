<template>

    <form action="" @submit.prevent="handleSubmit">
        <label for="">Title</label>
        <input type="text" v-model="title" required>

        <label for="">Details</label>
        <textarea name="" id="" cols="10" rows="5" v-model="details" required></textarea>

        <button> Add Project</button>
    
    </form>
  
</template>

<script>
export default {
    data(){
        return{
            title:'',
            details:'',
        }
    },
    methods:{
        handleSubmit(){
            let project = {
                title:this.title,
                details: this.details,
                completed: false,
            }
            fetch('http://localhost:3000/projects',{
                method:'POST',
                headers:{'Content-TYpe': 'application/json'},
                body: JSON.stringify(project)

            }).then(()=>{
                this.$router.push('/')
            })
        }
    
    }
    
}
</script>

<style>

form {
    
    background: white;
    border-radius: 10px;
    padding: 20px
    
}
label{
    display: block;
    padding: 20px 0 10px 0;
    font-size: 14px;
    font-weight: bold;
    text-transform: uppercase;
    color: #bbb
}
input{
    padding: 10px;
    border: 0;
    border-bottom: 1px solid #ddd;
    width: 100%;
    box-sizing:border-box
}
textarea{
    padding: 10px;
    border-bottom: 1px solid #ddd;
    width: 100%;
    box-sizing:border-box;
    height:100px;
}
form button{
    display: block;
    margin: 20px auto ;
    padding: 10px;
    background: #00ce89 ;
    color: #fff;
    border: 0;
    border-radius:6px;
    font-size: 16px;
}
</style>