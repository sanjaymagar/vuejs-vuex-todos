<template>
    <div id="events">
        <p>{{title}}</p>
        <p>hello sanjay</p>
        <button v-on:click= "increaseCounter(2)">Increase</button>
        <p>{{counter}}</p>
        <div v-on:mousemove="onMousemove">Co-ordinates: x: {{x}} || y: {{y}}
            <span v-on:mousemove.stop="">-DEAD SPOT</span> 
            <!-- event modifier -> stop propagation -->
        </div>
        <!-- key modifier -->
        <!-- alert when click enter and space key -->
        <input type="text" v-on:keyup.enter.space="alerMe">

        <!-- use condition on click event -->
        <div>
        <button type="text" v-on:click="counter++">Click Me</button>
        <p>{{(counter*2)> 10 ? 'Greater than 10' : 'Less than 10'}} {{counter}}</p>
        <p>Computed: {{incCounter}}</p>
        </div>

    </div>
</template>

<script>
export default {
    name: 'events',
    data() {
        return {
        title: 'hello world',
        counter: 0,
        x: 0,
        y: 0
        }    
    },
    methods: {
        increaseCounter: function(step) {
            this.counter += step; 
        },
        onMousemove: function(event) {
            this.x = event.clientX;
            this.y = event.clientY;
        },
        alerMe: function() {
            alert("Alert me when click enter or space keyboard event")
        }
    },
    computed: {
        incCounter: function() {
            return this.counter++;
        }
    },
    beforeCreate() {
        this.title = "Before Create!"
        console.log("before Created events has been consoled")
        
    },
    created() {
        this.title = "Created !"
        console.log("events has been created")
    },
    beforeMount() {
        console.log("events will be mounted")
    },
    mounted(){
        console.log("events has been mounted")
    },
    beforeUpdate() {
        console.log("Counter will be update")
    },
    beforeDestroy() {
        console.log("Counter will be destroy")
    },
    destroyed() {
        console.log("Counter has been destroyed")
    }
}
</script>

<style>

</style>
