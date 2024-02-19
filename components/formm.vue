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
  <form class="font-samim " >
    <v-card title="ربات جدید" class="pa-2" color="#f3f6fd"  subtitle="ربات ها امکان لورم اپسوم را فراهم میکنند" text="">
      
      <div class="" >
        <v-text-field v-model="state.name" :counter="10" label="نام" required></v-text-field>
  
        <v-text-field v-model="state.email" label="پست الکترونیک" required></v-text-field>
  
        <v-select v-model="state.select" :items="items" label="ایتم سمپل" required></v-select>
  
        <v-checkbox v-model="state.checkbox" label="Do you agree?" required></v-checkbox>
      لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت 
      لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت 
      لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت 
      لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت 
      لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت 
      لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت 
      </div>

      <VCardActions  >
        <v-btn class="me-4"> ثبت </v-btn>
        <v-btn > پاک کردن </v-btn>
      </VCardActions>
    </v-card>
  </form>
</template>

<style scoped></style>
