<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>First Name : {{ firstname }}</p>
    <p>Last Name : {{ lastname }}</p>
    <hr />
    <p>{{ fullname }}</p>
    <button @click="changename">ChangeName</button>
    <button @click="changenameSetter">Change Name Setter</button>
  </div>
</template>

<script>
export default {
  // name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      firstname: "umer",
      lastname: "khan"
    };
  },
  methods: {
    changename() {
      this.firstname = "bob";
      this.lastname = "bambbozled";
    },

    changenameSetter() {
      this.fullname = " Jazzy uzzy ";
    }
  },
  computed: {
    fullname: {
      get() {
        return `Full Name : ${this.firstname + " " + this.lastname}`;
      },

      set(newVal) {
        alert("setting Name :" + newVal);
        let newName = newVal.split(" ");
        this.firstname = newName[0];
        this.lastname = newName[newName.length - 1];
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
