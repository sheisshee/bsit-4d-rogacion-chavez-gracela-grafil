<script setup>
import { ref } from 'vue';

// Initial chat messages
let messages = ref([
  { text: 'Hello', sender: 'user' },
  { text: 'Hi there!', sender: 'bot' },
  { text: 'How are you?', sender: 'bot' },
]);

// Method to add a new message
const addMessage = (text, sender) => {
  messages.value.push({ text, sender });
};
</script>

<template>
  <div>
    <ul>
      <li v-for="message in messages" :key="message.text" :class="{ 'user-message': message.sender === 'user', 'bot-message': message.sender === 'bot' }">
        {{ message.text }}
      </li>
    </ul>
    <button @click="addMessage('Hello', 'user')">Send Message</button>
  </div>
</template>

<style scoped>
.user-message {
  color: blue;
}

.bot-message {
  color: green;
}
</style>
