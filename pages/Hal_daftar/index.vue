<template>
  <div class="form-container">
    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="form.email" required />
      </div>
      <div class="form-group">
        <label for="name">Nama</label>
        <input type="text" id="name" v-model="form.name" required />
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input type="password" id="password" v-model="form.password" required />
      </div>
      <button type="submit" class="submit-btn">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "PKLForm",
  data() {
    return {
      form: {
        email: "",
        name: "",
        password: "",
      },
    };
  },
  methods: {
    handleSubmit() {
      console.log("Form submitted:", this.form);
      alert("Pendaftaran berhasil!");
    },
  },
};

</script>

<style scoped>

.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: #ffffff;
}

form {
  width: 100%;
  max-width: 400px;
  background-color: #F3F3F3;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 15px;
}

label {
  display: block;
  font-size: 14px;
  margin-bottom: 5px;
  color: #333;
}

input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 14px;
  background-color: #ffffff;
}

.submit-btn {
  width: 100%;
  padding: 10px;
  background-color: #007BFF;
  color: black;
  border: none;
  border-radius: 4px;
  font-size: 14px;
  cursor: pointer;
}

.submit-btn:hover {
  background-color: #0056b3;
  color: white;
}
</style>
