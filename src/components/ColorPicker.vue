<template>
    <div>
        <Pixel isInColorPicker color="white" :current="color == 'white' ? true : false" />
        <Pixel isInColorPicker color="lightblue" :current="color == 'lightblue' ? true : false" />
        <Pixel isInColorPicker color="blue" :current="color == 'blue' ? true : false" />
        <Pixel isInColorPicker color="darkblue" :current="color == 'darkblue' ? true : false" />
    </div>
</template>
<script>
/* eslint-disable */
import Pixel from './Pixel'

export default {
    name: 'ColorPicker',
    components: {
        Pixel
    },
    props: {
        color: String,
    }
}
</script>