<template>
  <div class="hello">
    <p>{{ counter }}</p>
    <p>{{ fullName }}</p>
    <p>{{ fullName }}</p>

    <button v-on:click="counter++;">Increase Counter</button>
    <button v-on:click="changeName">Change Name</button>
    <button v-on:click="changeNameSetter">Change Name (setter)</button>
  </div>
</template>

<script>
export default {
  //name: "HelloWorld",
  data() {
    return {
      counter: 0,
      firstName: "Bo",
      lastName: "Andersen"
    };
  },
  methods: {
    changeName: function() {
      this.firstName = "Mark";
      this.lastName = "Gonzales";
    },
    changeNameSetter: function() {
      this.fullName = "Mark Gonzales";
    }
  },

  computed: {
    fullName: {
      get: function() {
        alert("Assembling full name...");
        return this.firstName + " " + this.lastName;
      },
      set: function(newValue) {
        alert("Setting new name: " + newValue);
        var parts = newValue.split(" ");
        this.firstName = parts[0];
        this.lastName = parts[parts.length - 1];
      }
    }
  }

  // computed: {
  //  fullname() {
  //       return `Full Name : ${this.firstname + " " + this.lastname}`;
  //     }
  // }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
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
</style>
