<!--
PRETTY CLOCK by Alexander Abraham, a.k.a. "Angel Dollface".
Licensed under the MIT license.
-->

<!--
We define where our dynamic data
appears on the page and what structure
it has.
-->
<template>
 <div class="time">
  <p class="time">
   {{ hours }}:{{ minutes }}:{{ seconds }}
  </p>
 </div>
</template>

<!--
We define our component, define the dynamic data
and manipulate it.
-->
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent(
    {
        // The component's name.
        name: 'ClockCog',

        // The data that will change.
        data () {
            return {
                hours: new Date().getHours().toString(),
                minutes: new Date().getMinutes().toString(),
                seconds: new Date().getSeconds().toString()
            }
        },
        methods: {

            // Gets the time.
            getTime() {
                let result: Array<string> = new Array();
                let date: Date = new Date();
                let hours: string = date.getHours().toString();
                let minutes: string = date.getMinutes().toString();
                let seconds: string = date.getSeconds().toString();
                result.push(hours);
                result.push(minutes);
                result.push(seconds);
                return result;
            },
        },

        // Updates the time every second.
        mounted() {
            setInterval(
                () => {
                    this.hours = this.getTime()[0];
                    this.minutes = this.getTime()[1];
                    this.seconds = this.getTime()[2];
                },
                1000
            );
        }
    }   
);
</script>