<template>
  <v-app>  
    <v-app-bar app>
      <v-toolbar-title>
        <g-link to="/">E-vents</g-link>
      </v-toolbar-title>

      <v-text-field
        v-model="searchText"
        @click:clear="searchText = ''"
        placeholder="Search"
        class="ml-8"
        style="max-width: 350px;"
        prepend-inner-icon="mdi-magnify"
        clearable
        outlined
        rounded
        dense
        hide-details
      />

      <v-spacer />
      <v-btn>Create Event</v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <v-row>
          <v-col sm="6" offset-sm="3">
            <slot :searchText="searchText" />
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName,
    siteDescription
  }
}
</static-query>

<script>
export default {
  data() {
    return {
      searchText: ''
    }
  }
}
</script>

<style scoped>
.v-toolbar__title a {
  text-decoration: none;
  color: #000;
}
</style>
