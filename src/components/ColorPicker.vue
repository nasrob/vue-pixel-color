<template>
    <div>
        <Pixel interactive color="white" :current="color == 'white' ? true : false" />
        <Pixel interactive color="lightblue" :current="color == 'lightblue' ? true : false" />
        <Pixel interactive color="blue" :current="color == 'blue' ? true : false" />
        <Pixel interactive color="darkblue" :current="color == 'darkblue' ? true : false" />
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