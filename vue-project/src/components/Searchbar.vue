<template>
<div>
    <form class="d-flex my-2 ">
        <input @input="onInput" class="rounded align-center mx-auto"  type="text" placeholder="Search.." name="search">
            
    </form>
    
</div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods: {
        onInput: function (event) {
            this.$emit('termChange', event.target.value);
        }
    }
};
</script>

<style scoped>

input[type="text"] {
    height: 40px;
    background-color:rgba(141, 125, 125, 0.185);
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: none;
    border-radius: 5px 0 0 5px;
}



</style>  