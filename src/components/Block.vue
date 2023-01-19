<template>
    <div class="block">
        Click me
    </div>
</template>
   
<script>
export default {
    props:['delay']

}
</script>

<style>
.block {
    width: 300px;
    height: 150px;
    background-color: rgb(32, 189, 110);
    margin: 0 auto;
    margin-top: 100px;
    cursor: pointer;
    text-align: center;
    line-height: 150px;
    font-size: 30px;
    color: white;
    border-radius: 10px;
}
</style>