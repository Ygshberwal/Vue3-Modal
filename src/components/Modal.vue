<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{dark: theme==='dark'}">
            <h1>{{ header }}</h1>
            <p>{{ text }}</p>
        </div>
    </div>
</template>


<script>
export default{
        props:['header', 'text', 'theme'],
        methods:{
            closeModal(){
                this.$emit('close')
            }
        }   
    }
</script>

<style>
.modal{
    width:400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
.backdrop{
    top:0%;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;

}
h1{
    color: aqua;
    border: none;
    padding: 0;
}
.modal.dark{
    background-color: black;
    color: white;
}
.modal.dark h1{
    color: white;
}

</style>

<!-- EXPORT IT TO IT'S PARENT COMPONENT -->