<script lang="ts" setup>
import { ref } from "vue";

const order = ref(0);

const open = ref(["Users"]);
const admins = ref([
  ["Management", "mdi-account-multiple-outline"],
  ["Settings", "mdi-cog-outline"],
]);
const cruds = ref([
  ["Create", "mdi-plus-outline"],
  ["Read", "mdi-file-outline"],
  ["Update", "mdi-update"],
  ["Delete", "mdi-delete"],
]);

const fav = ref(true),
  menu = ref(false),
  message = ref(false),
  hints = ref(true);

const menuContent = ref([
  {
    title: "بلاگ ها",
    value: "blogs",
    subItems: ["بلاگ های من"],
  },
  {
    title: "ارسال پیشرفته",
    value: "avancedSend",
    subItems: ["ربات های من", "متای جدید", "متای های من"],
  },
  {
    title: "اتوماسیون",
    value: "automation",
    subItems: ["کارتابل من", "ارسال نامه"],
  },
  {
    title: "تقویم",
    value: "calendar",
    subItems: ["کارتابل من", "ارسال نامه"],
  },
  {
    title: "حسابداری",
    value: "financial",
    subItems: ["کارتابل من", "ارسال نامه"],
  },
]);
</script>

<template>
  <v-layout class="rounded rounded-md">
    <vNavigationDrawer  location="left" color="light-blue-darken-4" permanent expand-on-hover rail>
      <v-list>
        <v-list-item @click="menu = !menu" prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
          title="Sandra Adams" subtitle="sandra_a88@gmailcom">
        </v-list-item>

        <v-menu v-model="menu" :close-on-content-click="false" location="end">
          <!-- <template v-slot:activator="{ props }">
          <v-btn  v-bind="props">
            Menu as Popover
          </v-btn>
        </template> -->

          <v-card min-width="300">
            <v-list>
              <v-list-item prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg" title="Sandra Adams"
                subtitle="sandra_a88@gmailcom">
                <template v-slot:append>
                  <v-btn variant="text" :class="fav ? 'text-yellow' : ''" icon="mdi-star" @click="fav = !fav"></v-btn>
                </template>
              </v-list-item>
            </v-list>

            <v-divider></v-divider>

            <v-list>
              <v-list-item>
                <v-switch v-model="message" color="purple" label="Enable messages" hide-details></v-switch>
              </v-list-item>

              <v-list-item>
                <v-switch v-model="hints" color="purple" label="Enable hints" hide-details></v-switch>
              </v-list-item>
            </v-list>

            <v-card-actions>
              <v-spacer></v-spacer>

              <v-btn variant="text" @click="menu = false"> Cancel </v-btn>
              <v-btn color="primary" variant="text" @click="menu = false">
                Save
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-menu>
      </v-list>

      <v-divider></v-divider>

      <v-list density="compact" nav>
        <v-list-item prepend-icon="mdi-folder" title="My Files" value="myfiles"></v-list-item>
        <v-list-item prepend-icon="mdi-account-multiple" title="Shared with me" value="shared"></v-list-item>
        <v-list-item prepend-icon="mdi-star" title="Starred" value="starred"></v-list-item>
      </v-list>
    </vNavigationDrawer>

    <v-navigation-drawer location="right" color="" permanent rail>
      <v-list density="comfortable" nav :color="'light-blue-darken-4'">
        <v-list-item prepend-icon="mdi-view-dashboard" title="dashboard" value="dashboard"></v-list-item>
        <v-list-item prepend-icon="mdi-star" title="Starred" value="starred"></v-list-item>

        <v-list-item prepend-icon="mdi-folder" title="My Files" value="myfiles" active></v-list-item>
        <v-list-item prepend-icon="mdi-content-save" title="ذخیره سازی" value="save"></v-list-item>
        <v-list-item prepend-icon="mdi-refresh-auto" title="اتوماسون" value="atoumation"></v-list-item>
        <v-list-item prepend-icon="mdi-lifebuoy" title="پشتیبانی" value="support"></v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-navigation-drawer permanent location="right" color="grey-lighten-5">
      <v-locale-provider rtl class="font-samim">
        <v-list density="compact" nav v-model:opened="open">
          <v-card class="mx-auto" :density="'compact'" color=" elevation-0">
            <template v-slot:title> خدمات </template>
          </v-card>
          <v-list-group collapse-icon="mdi-home" value="Users">
            <v-list-group v-for="item in menuContent" :key="item.value" :value="item.value">
              <template v-slot:activator="{ props }">
                <v-list-item :title="item.title" v-bind="props"></v-list-item>
              </template>

              <v-list-item v-for="(subItem, i) in item.subItems" :key="i" :title="subItem" :value="subItem"></v-list-item>
            </v-list-group>
          </v-list-group>
        </v-list>
      </v-locale-provider>
    </v-navigation-drawer>

    <v-app-bar :order="order" color="" flat>
      <v-app-bar-title>
        <div id="logo">
          <svg viewBox="0 0 406 146" preserveAspectRatio="xMidYMid meet" class="css-8aabad" id="fgedbhde">
            <defs id="SvgjsDefs1001"></defs>

            <g id="SvgjsG1007" fill="green" featurekey="LwVBM5-0"
              transform="matrix(1.0512660717352882,0,0,1.0512660717352882,263.44686692605393,-344.027483172063)">
              <switch xmlns="http://www.w3.org/2000/svg">
                <foreignObject requiredExtensions="http://ns.adobe.com/AdobeIllustrator/10.0/" x="0" y="0" width="1"
                  height="1"></foreignObject>
                <g xmlns:i="http://ns.adobe.com/AdobeIllustrator/10.0/" i:extraneous="self">
                  <path
                    d="M-240.5,401.7c5.6,1.6,20.9,6.6,21,6.7c1,0.3,1.5,1.4,1.2,2.4c-0.3,1-1.4,1.5-2.4,1.2c-0.2-0.1-15.4-5-20.9-6.6    c-2.2-0.6-3.5,0-4.3,0.8l30.9,16.8c2.2,1.2,4.9,1.5,7.3,0.8l24.4-7.3c0.5-0.2,1.1-0.1,1.5,0.2l12.6,7.9c1.8-1.9,5.4-6.4,5.8-12.4    l-22.3-9.6c-0.7-0.2-7.8-2.5-13.2,0l-13.1,6c0.3,0.9,1.1,1.9,2.9,2c4.5,0.1,11.8-1.3,11.9-1.3c1-0.2,2,0.5,2.2,1.5    c0.2,1-0.5,2-1.5,2.2c-0.3,0.1-7.8,1.5-12.7,1.4c-5.2-0.1-6.7-4.4-6.8-6.7c0-0.8,0.4-1.5,1.1-1.8l14.4-6.6c7-3.2,15.7-0.2,16-0.1    c0,0,0.1,0,0.1,0l23.5,10.2c0.7,0.3,1.1,1,1.1,1.7c0,10.2-7.8,17.1-8.1,17.4c-0.3,0.3-0.8,0.5-1.2,0.5c-0.3,0-0.7-0.1-1-0.3    l-13.1-8.2l-23.5,7.1c-3.4,1-7.1,0.6-10.2-1l-32.7-17.8c-0.8-0.4-1.2-1.4-0.9-2.3C-249.4,403.9-246.3,400-240.5,401.7z     M-216.4,365.3c-1,0-1.9,0.8-1.9,1.9v3.3h-0.6c-4,0-7.2,3.2-7.2,7.2c0,4,3.2,7.2,7.2,7.2h4.9c1.9,0,3.5,1.6,3.5,3.5    c0,1.9-1.6,3.5-3.5,3.5h-8.8c-1,0-1.9,0.8-1.9,1.9c0,1,0.8,1.9,1.9,1.9h4.5v3.3c0,1,0.8,1.9,1.9,1.9s1.9-0.8,1.9-1.9v-3.3h0.6    c4,0,7.2-3.2,7.2-7.2c0-4-3.2-7.2-7.2-7.2h-4.9c-1.9,0-3.5-1.6-3.5-3.5s1.6-3.5,3.5-3.5h8.6c1,0,1.9-0.8,1.9-1.9    c0-1-0.8-1.9-1.9-1.9h-4.3v-3.3C-214.5,366.1-215.3,365.3-216.4,365.3z">
                  </path>
                </g>
              </switch>
            </g>
            <g id="SvgjsG1008" featurekey="textGroupContainer" transform="matrix(1,0,0,1,405,0)" fill="#111">
              <rect xmlns="http://www.w3.org/2000/svg" y="0" height="1" width="1" opacity="0"></rect>
              <rect xmlns="http://www.w3.org/2000/svg" y="0" x="-290" width="3" height="146"></rect>
            </g>
            <g id="SvgjsG1009" featurekey="YhTCwJ-0"
              transform="matrix(2.586844010144754,0,0,2.586844010144754,132.48263292487573,24.376200934452797)"
              fill="#111">
              <path
                d="M2.02 10.64 l2.9 7.34 l0.04 0 l2.78 -7.34 l1.7 0 l-4.58 11.66 q-0.54 1.4 -1.23 1.95 t-1.83 0.55 q-0.86 0 -1.4 -0.24 l0.2 -1.36 q0.28 0.16 1.16 0.16 q1.12 0 1.62 -1.38 l0.7 -1.92 l-3.88 -9.42 l1.82 0 z M15.38 10.4 q2.08 0 3.25 1.31 t1.19 3.71 l0 0.38 l-7.56 0 q0.12 1.3 0.98 2.14 t2.1 0.86 q1.9 0 2.96 -1.42 l1.18 0.92 q-0.74 0.96 -1.74 1.45 t-2.4 0.49 q-2.14 0 -3.44 -1.39 t-1.32 -3.53 q0 -2.12 1.33 -3.5 t3.47 -1.42 z M18.14 14.48 q-0.06 -1.22 -0.79 -1.93 t-2.05 -0.71 q-1.2 0 -2.02 0.68 t-1.02 1.96 l5.88 0 z M23.8 4.880000000000001 l0 9.88 l4.26 -4.12 l2.22 0 l-4.52 4.26 l4.98 5.1 l-2.3 0 l-4.64 -4.92 l0 4.92 l-1.56 0 l0 -15.12 l1.56 0 z M33.160000000000004 5.84 q0.46 0 0.8 0.33 t0.34 0.81 q0 0.5 -0.32 0.82 t-0.82 0.32 t-0.82 -0.32 t-0.32 -0.82 q0 -0.48 0.34 -0.81 t0.8 -0.33 z M33.940000000000005 10.64 l0 11.44 q0 1.18 -0.7 1.94 t-2.06 0.78 q-0.66 0 -1.1 -0.2 l0.18 -1.36 q0.38 0.12 0.82 0.12 q1.3 0 1.3 -1.84 l0 -10.88 l1.56 0 z M40.64 10.4 q2.04 0 2.97 0.96 t0.95 2.9 l0 4.2 q0 0.6 0.14 1.54 l-1.5 0 q-0.1 -0.18 -0.1 -1.4 l-0.04 0 q-1.06 1.6 -3.08 1.64 q-1.54 0 -2.51 -0.77 t-0.97 -2.01 q0 -1.7 1.4 -2.49 t4.38 -0.79 l0.72 0 l0 -0.26 q0 -2.04 -2.32 -2.08 q-1.68 0 -2.78 1.02 l-0.98 -1.02 q1.44 -1.4 3.72 -1.44 z M38.18 17.3 q0 1.58 2.06 1.62 q1.22 0 1.99 -0.78 t0.77 -2.28 l0 -0.36 l-1.72 0 q-1.38 0 -2.23 0.44 t-0.87 1.36 z M52.040000000000006 10.4 q2.14 0 2.94 1.78 q0.56 -0.92 1.26 -1.35 t1.72 -0.43 q1.82 0 2.68 0.95 t0.86 2.87 l0 5.78 l-1.56 0 l0 -5.66 q0 -2.46 -2.28 -2.5 q-1.06 0 -1.74 0.79 t-0.68 1.91 l0 5.46 l-1.56 0 l0 -5.42 q0 -1.38 -0.4 -2.06 t-1.42 -0.68 q-1.42 0 -2.15 0.95 t-0.73 2.63 l0 4.58 l-1.56 0 l0 -7.28 q-0.02 -0.7 -0.08 -2.08 l1.48 0 q0.04 1.38 0.04 1.54 l0.04 0 q0.38 -0.8 1.22 -1.29 t1.92 -0.49 z M68.92 10.4 q2.18 0 3.56 1.35 t1.44 3.57 q0 2.14 -1.4 3.51 t-3.6 1.41 q-2.2 0 -3.58 -1.39 t-1.42 -3.53 q0 -2.16 1.4 -3.53 t3.6 -1.39 z M65.60000000000001 15.32 q0 1.54 0.93 2.49 t2.39 0.99 q1.46 0 2.38 -0.97 t0.94 -2.51 q0 -1.52 -0.93 -2.5 t-2.41 -0.98 q-1.44 0 -2.36 0.97 t-0.94 2.51 z M85.68 4.880000000000001 l0 15.12 l-1.56 0 l0 -1.66 l-0.04 0 q-0.48 0.9 -1.46 1.4 t-2.14 0.5 q-1.98 0 -3.31 -1.41 t-1.37 -3.51 q0 -2.14 1.37 -3.52 t3.55 -1.4 q2.02 0 3.36 1.6 l0.04 0 l0 -7.12 l1.56 0 z M77.48 15.32 q0 1.54 0.93 2.5 t2.39 0.98 q1.46 0 2.37 -0.96 t0.95 -2.52 q0 -1.52 -0.93 -2.5 t-2.41 -0.98 q-1.44 0 -2.35 0.97 t-0.95 2.51 z M89.48 5.84 q0.46 0 0.8 0.33 t0.34 0.81 q0 0.5 -0.32 0.82 t-0.82 0.32 t-0.82 -0.32 t-0.32 -0.82 q0 -0.48 0.34 -0.81 t0.8 -0.33 z M90.26 10.64 l0 9.36 l-1.56 0 l0 -9.36 l1.56 0 z M97.96 10.4 q0.36 0 0.64 0.1 l-0.1 1.58 q-0.44 -0.12 -0.84 -0.12 q-1.36 0 -2.05 0.89 t-0.69 2.51 l0 4.64 l-1.56 0 l0 -7.28 q0 -0.28 -0.08 -2.08 l1.48 0 q0.04 1.4 0.04 1.54 l0.04 0 q0.38 -0.8 1.23 -1.29 t1.89 -0.49 z">
              </path>
            </g>
            <g id="SvgjsG1010" featurekey="duLK5n-0"
              transform="matrix(0.7518219824414482,0,0,0.7518219824414482,132.53387009842885,95.00030764134601)"
              fill="#111">
              <path
                d="M6.3 20.14 c-0.48 0 -0.96 -0.06 -1.44 -0.16 c-1.48 -0.3 -2.94 -1.04 -4.24 -2.16 l1.18 -1.34 c1.06 0.92 2.24 1.54 3.42 1.78 c1 0.22 1.98 0.14 2.76 -0.22 c0.52 -0.24 1.42 -0.84 1.42 -2.06 c0 -1.5 -1.6 -2.04 -3.16 -2.34 c-0.14 -0.02 -2.38 -0.48 -3.28 -1 c-1.2 -0.72 -1.84 -1.8 -1.84 -3.12 c0 -0.74 0.24 -1.44 0.66 -2.06 c0.42 -0.56 1 -1.02 1.68 -1.34 c1 -0.48 2.18 -0.62 3.38 -0.42 c1.3 0.22 2.62 0.84 3.78 1.8 l-1.14 1.38 c-2.06 -1.7 -4.06 -1.74 -5.26 -1.18 c-0.82 0.38 -1.3 1.08 -1.3 1.8 c0 1.36 1.16 1.88 3 2.28 c0.76 0.18 2.34 0.44 3.28 0.98 c1.3 0.72 1.98 1.84 1.98 3.22 c0 0.82 -0.22 1.58 -0.68 2.24 c-0.42 0.6 -1.06 1.06 -1.78 1.42 c-0.76 0.38 -1.54 0.5 -2.42 0.5 z M26.48 20 l0 -14.24 l1.8 0 l0 12.5 l7.8 0 l0 1.74 l-9.6 0 z M56.64 5.32 c4.1 0 7.46 3.34 7.46 7.46 c0 4.1 -3.36 7.42 -7.46 7.42 s-7.44 -3.32 -7.44 -7.42 c0 -4.12 3.34 -7.46 7.44 -7.46 z M56.64 18.44 c3.12 0 5.64 -2.56 5.64 -5.66 c0 -3.12 -2.52 -5.7 -5.64 -5.7 s-5.64 2.58 -5.64 5.7 c0 3.1 2.52 5.66 5.64 5.66 z M85.96000000000001 10.84 l5.92 0 l0 6.3 c-1.42 1.9 -3.66 3.08 -6.02 3.08 c-4.1 0 -7.44 -3.34 -7.44 -7.46 c0 -4.1 3.34 -7.44 7.44 -7.44 c2.02 0 3.9 0.8 5.28 2.2 l-1.32 1.16 c-1.04 -1.04 -2.46 -1.6 -3.96 -1.6 c-3.14 0 -5.68 2.54 -5.68 5.68 c0 3.16 2.54 5.7 5.68 5.7 c1.66 0 3.18 -0.7 4.28 -1.92 l0 -3.94 l-4.18 0 l0 -1.76 z M116.8 20 l-1.58 -4.14 l-5.82 0 l-1.58 4.14 l-1.92 0 l5.48 -14.24 l1.86 0 l5.5 14.24 l-1.94 0 z M114.52 14.1 l-2.2 -5.76 l-2.22 5.76 l4.42 0 z M143.32 20 l-7.62 -11.26 l0 11.26 l-1.8 0 l0 -14.24 l1.96 0 l7.6 11.26 l0 -11.26 l1.8 0 l0 14.24 l-1.94 0 z M181.88 20 l0 -12.48 l-3.76 0 l0 -1.76 l9.32 0 l0 1.76 l-3.76 0 l0 12.48 l-1.8 0 z M202.20000000000002 20 l0 -14.24 l9 0 l0 1.72 l-7.2 0 l0 3.34 l6.28 0 l0 1.78 l-6.28 0 l0 5.64 l7.02 0 l0 1.76 l-8.82 0 z M235.92000000000002 20 l-4.26 -5.96 l-4.28 5.96 l-2.18 0 l5.36 -7.48 l-4.84 -6.76 l2.2 0 l3.74 5.22 l3.74 -5.22 l2.18 0 l-4.84 6.76 l5.36 7.48 l-2.18 0 z M255.76000000000002 20 l0 -12.48 l-3.76 0 l0 -1.76 l9.32 0 l0 1.76 l-3.76 0 l0 12.48 l-1.8 0 z">
              </path>
            </g>
          </svg>
        </div>
      </v-app-bar-title>
      <template v-slot:append>
        <!-- <v-switch
          v-model="order"
          hide-details
          inset
          label="Toggle order"
          true-value="-1"
          false-value="0"
        ></v-switch> -->
        <h2 class="text-h5 font-samim" style="color: #01579b;" >ثبت ربات جدید</h2>
      </template>
    </v-app-bar>

    <v-locale-provider rtl>
      <v-main class="" style="min-height: 300px; background-color: #fff; position: relative">
        <v-breadcrumbs bg-color="grey-lighten-5" :items="['Foo', 'Bar', 'Fizz']"></v-breadcrumbs>
        <VContainer>
          <VRow>
            <VCol cols="6">
              <Formm />
            </VCol>
          </VRow>
        </VContainer>
      </v-main>
    </v-locale-provider>
    <VLayoutItem model-value position="bottom" class="text-end" size="88" absolute>
      <div class="ma-4" style="position: relative">
        <v-btn size="x-large" min-height="65" class="me-2 text-none rounded-xl elevation-2" color="primary"
          prepend-icon="mdi-plus" variant="flat">
          New
          <v-menu activator="parent">
            <v-list>
              <v-list-item v-for="(item, index) in menuContent" :key="index" :value="index" class="font-samim">
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </v-btn>
      </div>
    </VLayoutItem>
  </v-layout>
</template>

<style scoped lang="scss">
#logo {
  width: max-content;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 8px;

  svg {
    width: 140px;
  }
}
</style>
