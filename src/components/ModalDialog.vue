<script setup lang="ts">
import { ref, defineProps, defineEmits } from 'vue'
import axios from 'axios'

defineProps({
  isShow: Boolean
})

const emit = defineEmits(['update:isShow'])

const TELEGRAM_TOKEN = '7423222238:AAExBK8OQDofB8U8YfUM3qzIuXVTx7e21-o'
const TELEGRAM_CHAT_ID = '1177010462'

const firstName = ref('')
const lastName = ref('')
const email = ref('')

function hideDialog() {
  emit('update:isShow', false)
}

function escapeMarkdownV2(text: string): string {
  return text.replace(/([_*\[\]()~`>#+\-=|{}.!])/g, '\\$1').replace(/(\d+)(\.)(\d+)/g, '$1\\.$3')
}

async function submitForm() {
  const message = `
*New Contact Submission*
*First Name:* ${escapeMarkdownV2(firstName.value)}
*Last Name:* ${escapeMarkdownV2(lastName.value)}
*Email:* ${escapeMarkdownV2(email.value)}
  `

  try {
    await axios.post(`https://api.telegram.org/bot${TELEGRAM_TOKEN}/sendMessage`, {
      chat_id: TELEGRAM_CHAT_ID,
      text: message,
      parse_mode: 'MarkdownV2'
    })
    hideDialog()
  } catch (error) {
    console.error('Error sending message:', error)
  }
}
</script>

<template>
  <div
    v-if="isShow"
    class="fixed inset-0 flex items-center justify-center bg-gray-500 bg-opacity-75 z-50"
    @click="hideDialog"
  >
    <div class="bg-white p-10 rounded-lg shadow-lg w-full max-w-md" @click.stop>
      <h2 class="text-3xl font-bold text-center mb-6">Заполните форму</h2>
      <div class="space-y-6">
        <div>
          <label for="first-name" class="block text-sm font-medium text-gray-900">First name</label>
          <div class="mt-2">
            <input
              v-model="firstName"
              type="text"
              id="first-name"
              class="block w-full rounded-md border-0 py-2.5 pl-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
            />
          </div>
        </div>

        <div>
          <label for="last-name" class="block text-sm font-medium text-gray-900">Last name</label>
          <div class="mt-2">
            <input
              v-model="lastName"
              type="text"
              id="last-name"
              class="block w-full rounded-md border-0 py-2.5 pl-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
            />
          </div>
        </div>

        <div>
          <label for="email" class="block text-sm font-medium text-gray-900">Email address</label>
          <div class="mt-2">
            <input
              v-model="email"
              id="email"
              type="email"
              class="block w-full rounded-md border-0 py-2.5 pl-3 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
            />
          </div>
        </div>
      </div>

      <button
        @click="submitForm"
        type="button"
        class="mt-2.5 rounded-md bg-indigo-600 px-3 py-3 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-600"
      >
        Отправить
      </button>
    </div>
  </div>
</template>

<style scoped>
/* Additional scoped styles if needed */
</style>
