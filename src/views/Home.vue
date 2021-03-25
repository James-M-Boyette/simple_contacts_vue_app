<template>
  <div class="home">
    <h3>{{ message }}</h3>
    <h1>Your contacts, here!</h1>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      message: "Let's try and make a Vue Contacts app from scratch!",
      contacts: [],
    };
  },
  created: function () {
    console.log("in created ...");
    this.contactsIndex();
  },
  methods: {
    contactsIndex: function () {
      console.log("Our Contacts will be displayed ...");
      axios.get("http://localhost:3000/api/contacts").then((response) => {
        console.log(response.data);
        this.contacts = response.data;
      });
    },
  },
};
</script>

// We need to see if we can do an index action, first as a method, and then as an auto, using "created"
