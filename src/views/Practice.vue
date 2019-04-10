<template>
<!-- reference https://vuejs.org/v2/guide/forms.html#v-model-with-Components -->
<div class="practice">
    <!-- <p v-if= "show">Hello sanjay lafa magar</p> -->
    <!-- <p v-show="!show">Konichiwa</p> -->
    <!-- <button @click="show = !show">Switch Me</button> -->
    <!-- <p :key="i" v-for="(day, i) in weekDay"> {{day}} ({{i}}) </p> -->
    <!-- <p :key="obj.id" v-for="obj in object"> {{obj}} </p> -->

    <!-- j v-model ma bind gareko xa tehi nai input ma display hunxa -->
    <!-- <input v-model="message" placeholder="edit me"> 
    <p>Message is: {{ message }}</p> -->

    <!-- interpolation {{}} won't work on textarea so use instead v-model -->
    <!-- <textarea v-model="text" placeholder="Type..."/>
    <p>Text: {{text}}</p> -->

    <!-- <input type="checkbox" id="checkbox" v-model="checked">
    <label for="checkbox">{{ checked }}</label> -->
    <!-- <div id="multi-checkbox">
        <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
        <label for="jack">Jack</label>
        <input type="checkbox" id="john" value="John" v-model="checkedNames">
        <label for="john">John</label>
        <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
        <label for="mike">Mike</label>
        <br>
        <span>Checked names: {{ checkedNames }}</span>
    </div> -->

    <div>
        <p :key="i" v-for="(day, i) in weekDay">
        <input type="checkbox" id="i" :value="day" v-model="checkedNames">
        <label for="i">{{day}}</label>
        </p>
        {{checkedNames}}
    </div>

    <!-- <div>
        <ul class="">
            <li v-for="(day, i) in weekDay" :key="i">
                <input type="checkbox" id="i" value="day" v-model="checkBox">
                <label for="i"> {{ day }} </label>
            </li>
        </ul>
    </div> -->

    <!-- <div id="radio">
        <input type="radio" id="one" value="One" v-model="picked">
        <label for="one">One</label>
        <br>
        <input type="radio" id="two" value="Two" v-model="picked">
        <label for="two">Two</label>
        <br>
        <span>Picked: {{ picked }}</span>
    </div> -->

    <div class="options">
        <select v-model="selected">
            <option :key="day" v-for="day in weekDay" :value="day">
                {{day}}
            </option>
        </select>
        <br><hr>
        <span>Selected: {{selected}}</span>
        <hr>
    </div>

    <!-- <select class="form-control" v-model="groupName">
        <option v-for="grpName in allGroupName" v-bind:value="groupName">
            {{grpName}} 
        </option>
    </select> -->

</div>
</template>

<script>
export default {
    name: "practice",
    data: function() {
        return{
            selected:"Monday",
            // picked:"Picked",
            // radio: radio,
            checkedNames: ['Tuesday'],
            options: '',
            // checked: true,
            // show:true,
            // text: konichiwa,
            // message: "arigato gozaimasu and arigato Gozaimashita",
            weekDay: ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"],
            // object: {
            //     firstName:"Sanjay",
            //     middleName: "Gharti",
            //     lastName: "Magar"
            // }
        }
    }
}
</script>

<style scoped>
 .practice {
     text-align: center;
     margin-top: 20px;
 }
 .options {
     margin-top: 30px;
 }
</style>
