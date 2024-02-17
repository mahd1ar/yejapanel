<script lang="ts" setup>
import { reactive } from "vue";

const initialState = {
  name: "",
  email: "",
  select: null,
  checkbox: null,
};

const state = reactive({
  ...initialState,
});

const items = ["Item 1", "Item 2", "Item 3", "Item 4"];

// const v$ = useVuelidate(rules, state)

// function clear () {
//   v$.value.$reset()

//   for (const [key, value] of Object.entries(initialState)) {
//     state[key] = value
//   }
// }
</script>

<template>
  <form>
    <v-card title="Card title" class="pa-2" color="#f3f6fd"  subtitle="Subtitle" text="...">
      
      <div class="" >
        <v-text-field v-model="state.name" :counter="10" label="Name" required></v-text-field>
  
        <v-text-field v-model="state.email" label="E-mail" required></v-text-field>
  
        <v-select v-model="state.select" :items="items" label="Item" required></v-select>
  
        <v-checkbox v-model="state.checkbox" label="Do you agree?" required></v-checkbox>
      
      </div>

      <v-card-actions>
        <v-btn class="me-4"> submit </v-btn>
        <v-btn @click="clear"> clear </v-btn>
        <v-btn>Click me</v-btn>
      </v-card-actions>
    </v-card>
  </form>
</template>

<style scoped></style>
