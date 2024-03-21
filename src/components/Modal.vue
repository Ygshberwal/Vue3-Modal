<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{dark: theme==='dark'}">
            <slot>Default content. This will only show when we don't pass in default slot</slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
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
.modal .actions{
    text-align: center;
    margin: 30px 0 10px 0;
}
.modal .actions a{
    color: #f88a8a;
    padding: 8px;
    margin: 10px;
    border: 1px solid #f2d9d9;
    border-radius: 4px;
    text-decoration: none;
}
.modal.dark{
    background-color: black;
    color: white;
}
.modal.dark h1{
    color: white;
}
.modal.dark .actions{
    color: #e35353;
}
.modal.dark .actions a{
    color: #e35353;
}
</style>

<!-- EXPORT IT TO IT'S PARENT COMPONENT -->