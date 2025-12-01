<template>
  <div class="settings-page">

    <div class="header">
      <v-icon size="40" color="#0078D4">mdi-cog-outline</v-icon>
      <div class="ml-3">
        <h2 class="title">Settings</h2>
        <p class="sub">Manage system preferences</p>
      </div>
    </div>

    <v-card elevation="1" class="settings-card mt-6">
      
      <h3 class="section-title">General</h3>

      <v-switch
        v-model="darkMode"
        label="Enable Dark Mode"
        color="#0078D4"
      />

      <v-switch
        v-model="emailAlerts"
        label="Email Alerts"
        color="#0078D4"
      />

      <v-divider class="my-4"></v-divider>

      <h3 class="section-title">Locale</h3>

      <v-select
        label="Language"
        v-model="language"
        :items="['English', 'French', 'Spanish']"
        variant="outlined"
      />

      <v-text-field
        label="Timezone"
        variant="outlined"
        v-model="timezone"
      />

      <v-btn
        color="#0078D4"
        class="mt-6"
        variant="flat"
        style="color: white;"
      >
        Save Settings
      </v-btn>

    </v-card>

  </div>
</template>

<script setup>
import { ref } from 'vue'

const darkMode = ref(false)
const emailAlerts = ref(true)
const language = ref('English')
const timezone = ref('UTC')
</script>

<style scoped>
.settings-page {
  padding: 20px;
}

.header {
  display: flex;
  align-items: center;
}

.title {
  font-size: 22px;
  font-weight: 600;
}

.sub {
  font-size: 14px;
  margin-top: 2px;
  color: #666;
}

.settings-card {
  padding: 20px;
  border-radius: 12px;
}

.section-title {
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 10px;
}
</style>
