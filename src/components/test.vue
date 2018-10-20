<template>
  <div class="test">
  <input type="text" v-model="title"><br />
    <h1>{{title}}</h1>
    <p v-if="showName">{{user.firstName}}</p>
    <p v-else="showName">Nobody</p>
    <ul>
      <li v-for="item in items">{{item.title}}</li>
    </ul>
    <button v-on:click="greet('Heeeellllooo Skurrywesyny')">Say Greeting</button>
    <br />
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    <hr />
    <label> First Name: </label><input type="text" v-model="user.firstName">
    <br />
      <label> Last Name: </label><input type="text" v-model="user.lastName">
    <h3>{{fullName}}</h3>
    <h2>{{msg}} </h2>
  </div>
</template>

<script>
  export default {
    name: 'test',
    props: {
    msg: {
      type: String,
      default: 'Foobar'
      }
    },
    data() {
    return {
      title: 'Hello World',
      user: {
        firstName: 'John',
        lastName: 'Doe'
        },
        showName: false,
        items: [
          {title: "item One"},
          {title: "item Two"},
          {title: "item Three"}
        ]
      }
    },
    methods: {
      greet: function(greeting) {
      alert(greeting)
      },
      pressKey: function(e) {
      console.log(e.target.value);
      },
      enterHit: function() {
        console.log('You hit enter');
      }
    },
    computed: {
    fullName: function() {
    return this.user.firstName + " " + this.user.lastName;
    }
    }
  }
</script>

<style scoped>

</style>
