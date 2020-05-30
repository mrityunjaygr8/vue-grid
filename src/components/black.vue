<template>
    <div class="item item-black">
        {{ extra }}
    </div>
</template>
<script>
export default {
    name: "Black",
    props: ["extra"]
}
</script>
<style>
    .item-black {
        background-color: black;
        color: white;
    }
</style>