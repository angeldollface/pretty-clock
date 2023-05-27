<!--
PRETTY CLOCK by Alexander Abraham, a.k.a. "Angel Dollface".
Licensed under the MIT license.
-->

<!--Load all components and use them.-->
<template>
 <ClockCog/>
</template>
   
<!--
Register our "App", import our components, 
and register those with the "App".
-->
<script lang="ts">
import { defineComponent } from 'vue';
import ClockCog from './ClockCog.vue';
   
export default defineComponent(
    {
        name: 'App',
        components: {
            ClockCog
        }
    }   
);
</script>
   
<!--
Styling our app. We use SASS
because I love it.
-->
<style lang="scss">
// Setting our layout variables.
$stdFont: 'DotMatrix';
$mainColor: #FFFFFF;
$accentColor: #000000;
$shadowColor: #808080;
   
// Importing our stylesheets.
@import './sass/desktop';
@import './sass/responsive';
</style>
