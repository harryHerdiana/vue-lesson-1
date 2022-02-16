<template>
  <form @submit.prevent="submitData">
    <div>
      <label for="nameInput">Name</label>
      <input v-model="enteredName" name="nameInput" type="text" />
    </div>
    <div>
      <label for="phoneInput">Phone</label>
      <input v-model="enteredPhone" name="phoneInput" type="text" />
    </div>
    <div>
      <label for="emailInput">E-Mail</label>
      <input v-model="enteredEmail" name="emailInput" type="text" />
    </div>
    <button>Add contact</button>
  </form>
</template>

<script>
export default {
  emits: ["add-contact"],
  data() {
    return {
      enteredName: "",
      enteredPhone: "",
      enteredEmail: "",
    };
  },
  methods: {
    submitData() {
      this.$emit(
        "add-contact",
        this.enteredName,
        this.enteredPhone,
        this.enteredEmail
      );
    },
  },
};
</script>