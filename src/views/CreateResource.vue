<template>
  <div class="create-resource-page">

    <!-- PAGE TITLE -->
    <h2 class="title">Create a resource</h2>

    <!-- TOP BUTTONS -->
    <div class="top-buttons">
      <v-btn variant="text">Help me build an application</v-btn>
      <v-btn variant="text">Choose the right VM size</v-btn>
      <v-btn variant="text">Low-cost VM options</v-btn>
    </div>

    <v-divider class="my-4"></v-divider>

    <v-row>


      <!-- LEFT CATEGORY SIDEBAR -->

      <v-col cols="12" md="3">
        <v-card elevation="0" class="category-sidebar pa-2">

          <v-list density="compact">

            <v-list-subheader class="sub">Get Started</v-list-subheader>
            <v-list-item>Recently created</v-list-item>

            <v-divider class="my-2"></v-divider>

            <v-list-subheader class="sub">Categories</v-list-subheader>

            <v-list-item v-for="c in categories" :key="c">
              {{ c }}
            </v-list-item>

          </v-list>

        </v-card>
      </v-col>



      <!-- MAIN CONTENT -->
      <v-col cols="12" md="9">

        <!-- SEARCH SERVICES -->
        <v-text-field
          prepend-inner-icon="mdi-magnify"
          label="Search services and marketplace"
          class="mb-6"
        ></v-text-field>

        <!-- POPULAR AZURE SERVICES -->
        <h3 class="section-label">Popular Azure services</h3>

        <v-row dense class="mt-2">
          <v-col
            cols="12"
            md="6"
            v-for="svc in azureServices"
            :key="svc.name"
          >
            <v-card elevation="0" class="service-item pa-3 d-flex align-center">

              <v-avatar size="40" class="mr-3">
                <v-icon>{{ svc.icon }}</v-icon>
              </v-avatar>

              <div>
                <div class="service-name">{{ svc.name }}</div>
                <v-btn
                  variant="text"
                  size="small"
                  @click="goCreate(svc.name)"
                >
                  Create
                </v-btn>
              </div>

            </v-card>
          </v-col>
        </v-row>

        <!-- POPULAR MARKETPLACE -->
        <h3 class="section-label mt-10">Popular Marketplace products</h3>

        <v-row dense class="mt-2">
          <v-col
            cols="12"
            md="6"
            v-for="prod in products"
            :key="prod.name"
          >
            <v-card elevation="0" class="product-item pa-3 d-flex align-center">

              <v-avatar rounded size="40" class="mr-3">
                <img :src="prod.img" alt="icon" />
              </v-avatar>

              <div>
                <div class="prod-name">{{ prod.name }}</div>
                <v-btn variant="text" size="small">Create</v-btn>
                <v-btn variant="text" size="small">Learn more</v-btn>
              </div>

            </v-card>
          </v-col>
        </v-row>

      </v-col>

    </v-row>

  </div>
</template>

<script setup>
const categories = [
  "Machine Learning",
  "AI Apps and Agents",
  "Analytics",
  "Blockchain",
  "Infrastructure Services",
  "Databases",
  "Developer Tools",
  "DevOps",
  "Identity",
  "Integration",
  "IoT",
  "IT & Management Tools",
  "Media",
  "Migration",
  "Mixed Reality",
  "Monitoring",
  "Security",
  "Storage",
  "Web"
]

const azureServices = [
  { name: "Function App", icon: "mdi-lightning-bolt" },
  { name: "Web App", icon: "mdi-web" },
  { name: "Virtual Network", icon: "mdi-lan" },
  { name: "Resource Group", icon: "mdi-folder" },
  { name: "Virtual Machine", icon: "mdi-server" },
  { name: "Storage Account", icon: "mdi-database" },
]

const products = [
  { name: "Windows Server 2022", img: "/windows.png" },
  { name: "Ubuntu Server 22.04", img: "/ubuntu.png" },
  { name: "SQL Server Developer", img: "/sql.png" },
  { name: "Red Hat Linux", img: "/redhat.png" },
]
const goCreate = (name) => {
  console.log("Open Create flow:", name)
}
</script>

<style scoped>
.create-resource-page {
  padding: 20px;
}

.title {
  font-size: 24px;
  font-weight: 700;
}

.sub {
  font-size: 12px;
  opacity: 0.7;
}

.category-sidebar {
  border-right: 1px solid #e3e3e3;
  height: 100%;
}

.section-label {
  font-size: 18px;
  font-weight: 600;
}

.service-item:hover,
.product-item:hover {
  background: #f3f7ff;
}

.service-name,
.prod-name {
  font-weight: 600;
  font-size: 16px;
}
</style>
