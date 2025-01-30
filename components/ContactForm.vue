<template>
  <div class="form-wrapper">
    <form @submit.prevent="submitForm">
      <label for="name">Name:</label>
      <input type="text" id="name" v-model="form.name" required />

      <label for="email">Email:</label>
      <input type="email" id="email" v-model="form.email" required />

      <label for="message">Message:</label>
      <textarea id="message" v-model="form.message" required></textarea>

      <button type="submit">Submit</button>
    </form>
    <p v-if="successMessage" class="success">{{ successMessage }}</p>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const form = ref({
      name: "",
      email: "",
      message: "",
    });

    const successMessage = ref("");

    const submitForm = async () => {
      try {
        const response = await fetch("https://formspree.io/f/xyyrryrr", {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify(form.value),
        });

        if (response.ok) {
          successMessage.value = "Message sent successfully!";
          form.value = { name: "", email: "", message: "" };
        } else {
          throw new Error("Failed to send message.");
        }
      } catch (error) {
        console.error(error);
        successMessage.value = "An error occurred. Please try again.";
      }
    };

    return { form, successMessage, submitForm };
  },
};
</script>

<style scoped>
/* Outer wrapper to center everything */
.form-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

/* Labels */
label {
  display: block;
  font-size: 1.2rem;
  font-weight: bold;
  color: black;
  margin-bottom: 5px;
  text-align: left;
}

/* Input fields & textarea */
input,
textarea {
  display: block;
  width: 100%;
  padding: 12px;
  margin-bottom: 15px;
  font-size: 1rem;
  border: none;
  border-radius: 15px;
  outline: none;
  background: #fff8e1;
  box-shadow: inset 2px 2px 5px rgba(0, 0, 0, 0.1);
}

/* Remove border and focus glow */
input:focus,
textarea:focus {
  background: #fff3cd;
  box-shadow: none;
}

/* Textarea size */
textarea {
  min-height: 120px;
  resize: none;
}

/* Submit button */
button {
  width: 100%;
  padding: 12px;
  font-size: 1.2rem;
  font-weight: bold;
  border: none;
  border-radius: 15px;
  cursor: pointer;
  background: #ff9800;
  color: white;
  text-transform: uppercase;
  box-shadow: 4px 4px 8px rgba(0, 0, 0, 0.2);
  transition: 0.3s;
}

/* Hover effect for button */
button:hover {
  background: #e65100;
}

/* Success message */
.success {
  color: #2e7d32;
  font-size: 1.2rem;
  font-weight: bold;
  margin-top: 10px;
}
</style>
