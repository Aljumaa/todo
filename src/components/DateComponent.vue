<template>
    <div>
        <ul class="list-group">
          <li class="list-group-item" v-show="date"><strong>Date:</strong> {{ date }}</li>
          <li class="list-group-item" v-show="time"><strong>Time:</strong> {{ time }}</li>
        </ul>
    </div>  
</template>

<script>
    export default {
        name: "DateComponent",
        data: () => ({
          date: '',
          time: '',
        }),
        methods: {
          printDate: function () {
            return new Date().toLocaleDateString();
          },
          printTime: function () {
            return new Date().toLocaleTimeString();
          },
        },
        mounted: function () {
          this.date = this.printDate();
          this.time = this.printTime();
        },
    };
</script>