<template>
  <div>
    <v-toolbar app flat>
      <v-toolbar-title>{{ this.$site.title }}</v-toolbar-title>  
      <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn flat :to=/about/>About</v-btn>
      <v-btn flat :to=/contact/>Contact</v-btn>
    </v-toolbar-items>
    </v-toolbar>
  </div>
</template>
