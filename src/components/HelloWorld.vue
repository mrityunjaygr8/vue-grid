<template>
    <div class="hello">
        <div id="header">
            <button>Click me</button>
            <button>Click me again</button>
        </div>
        <br>
        <div id="layout">
            <g-layout
                :layout.sync="grid"
                :col-num="12"
                :row-height="30"
                :is-draggable=drag
                :is-resizable=resize
                :is-mirrored="false"
                :vertical-compact="true"
                :margin="[10, 10]"
                :use-css-transforms="true"
                :static="true"
                :maxW="10">
                <!-- <base-item v-for="i in grid" :data="i" :key="i.i" /> -->
                <g-item v-for="i in grid" :x="i.x" :y="i.y" :w="i.w" :h="i.h" :i="i.i" :key="i.i" >
                    <component :is="i.comp" :extra="i.i" />
                    <!-- <black :extra="i.i" />
                    <white :extra="i.i" /> -->
                </g-item>
            </g-layout>
        </div>
    </div>
</template>

<script>
import VueGridLayout from 'vue-grid-layout';
import White from '@/components/white.vue';
import Black from '@/components/black.vue';
export default {
    name: 'HelloWorld',
    components: {
        "g-layout": VueGridLayout.GridLayout,
        "g-item": VueGridLayout.GridItem,
        "white": White,
        "black": Black
    },
    data() {
        return {
            drag: true,
            resize: true,
            grid: [
                {"x":0,"y":0,"w":2,"h":2,"i":"0", "comp": White},
                {"x":2,"y":0,"w":2,"h":4,"i":"1", "comp": Black},
                {"x":4,"y":0,"w":2,"h":5,"i":"2", "comp": White},
                {"x":6,"y":0,"w":2,"h":3,"i":"3", "comp": Black},
            ]
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.item {
    width: 100%;
    height: 100%;
}
</style>
