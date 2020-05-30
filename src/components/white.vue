<template>
    <div class="item item-white">
        {{ extra }}
    </div>
</template>
<script>
export default {
    name: "White",
    props: ["extra"]
}
</script>
<style>
    .item-white {
        color: black;
        background-color: white;
    }
</style>