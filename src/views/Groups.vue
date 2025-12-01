<template>
  <div class="groups-page">

    <!-- PAGE HEADER -->
    <div class="groups-header">
      <v-icon size="40" color="#0078D4">mdi-account-group</v-icon>

      <div class="ml-3">
        <h2 class="title">Groups</h2>
        <p class="subtitle">Manage user groups</p>
      </div>
    </div>

    <!-- CONTENT BOX -->
    <v-card elevation="1" class="content-box mt-6">

      <!-- TOP ACTION BAR -->
      <div class="action-bar">
        <v-btn 
          color="#0078D4"
          variant="flat"
          class="create-btn"
        >
          <v-icon left>mdi-account-multiple-plus</v-icon>
          Create Group
        </v-btn>
      </div>

      <!-- GROUPS TABLE -->
      <v-table class="mt-4 azure-table">
        <thead>
          <tr>
            <th class="table-head">ID</th>
            <th class="table-head">Group Name</th>
            <th class="table-head">Members</th>
            <th class="table-head">Last Updated</th>
          </tr>
        </thead>

        <tbody>
          <tr v-for="g in groups" :key="g.id">
            <td>{{ g.id }}</td>
            <td>{{ g.name }}</td>
            <td>{{ g.members }}</td>
            <td>{{ g.updated }}</td>
          </tr>
        </tbody>

      </v-table>

    </v-card>

  </div>
</template>

<script setup>
const groups = [
  { id: 1, name: "Admins", members: 4, updated: "2025-02-20" },
  { id: 2, name: "Editors", members: 12, updated: "2025-02-18" },
  { id: 3, name: "Viewers", members: 30, updated: "2025-02-10" },
]
</script>

<style scoped>
.groups-page {
  padding: 20px;
}

.groups-header {
  display: flex;
  align-items: center;
}

.title {
  font-size: 22px;
  font-weight: 600;
  margin: 0;
}

.subtitle {
  font-size: 14px;
  margin-top: 2px;
  color: #666;
}

.content-box {
  padding: 20px;
  border-radius: 12px;
}

.action-bar {
  display: flex;
  justify-content: flex-end;
}

.create-btn {
  text-transform: none;
  color: white !important;
  border-radius: 6px;
}

.table-head {
  text-align: left;
  font-size: 14px;
  font-weight: 600;
  color: #444;
}

.azure-table tbody tr:hover {
  background: #eef4fb;
}
</style>
