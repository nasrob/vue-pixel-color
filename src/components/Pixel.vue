<template>
    <div @click="handleClick" :class="['pixel', color, current ? 'current' : '']"></div>
</template>
<script>
export default {
    name: 'Pixel',
    props: {
        color: String,
        current: Boolean,
        isInColorPicker: Boolean,
        isInCanvas: Boolean,
        index: Number
    },
    methods: {
        handleClick: function() {
            if (this.isInColorPicker) {
                this.eventBus.emit('updatecolor', this.color)                
            }

            if (this.isInCanvas) {
                this.eventBus.emit('clickedpixel', this.index)
            }
        }
    }
}
</script>
<style scoped>
.pixel {
    border: 1px solid lightgray;
    width: 30px;
    height: 30px;
    box-sizing: border-box;
}

.white {
    background-color: white;
} 
.lightblue {
    background-color: rgb(0, 188, 212);
} 
.blue {
    background-color: rgb(3, 169, 244);
} 
.darkblue {
    background-color: rgb(33, 150, 243);
}

.pixel.current {
    border: 4px solid yellow;
}
</style>