<template>
  <div class="container">
    <h1 class="title">Welcome to my second assignment</h1>
    <div class="form-container">
      <p>Silahkan abang isi kotak teks di bawah ini:</p>
      <input
        type="text"
        v-model="inputText"
        placeholder="Isi apa aja bang..."
        :class="{ highlight: inputText.includes('Vue') }"
        :style="{ 'font-weight': inputText.length > 10 ? 'bold' : 'normal' }"
        class="text-input"
        @input="handleInputChange"
      />
      <p>
        Data yang abang masukkan:
        <br />
        <span class="wrapped-text">{{ inputText }}</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: "",
    };
  },
  methods: {
    handleInputChange(event) {
      console.log("Nilai input berubah:", event.target.value);
    },
  },
  watch: {
    inputText(newValue, oldValue) {
      console.log("Nilai input berubah:", newValue);
    },
  },
};
</script>

<style>
.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #dedede;
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  transform: translateX(5%);
}

.title {
  font-family: Georgia, "Times New Roman", Times, serif;
  text-align: center;
  color: #2f8e28;
}

.form-container {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
}

.form-container p {
  font-family: sans-serif;
}

.text-input {
  width: 95%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.3s ease;
  word-wrap: break-word;
}

.text-input:focus {
  border-color: #2f8e28;
}

.highlight {
  background-color: yellow;
}

p {
  margin: 10px 0;
  color: #555;
}

.wrapped-text {
  display: block;
  max-width: 100%;
  overflow-wrap: break-word;
  font-family: "Courier New", Courier, monospace;
  color: #2f8e28;
}
</style>
