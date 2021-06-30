<template>
  <!-- <hello-world /> -->
  <div>
    <v-tabs
      v-model="tab"
      fixed-tabs
      :background-color="$vuetify.theme.dark ? 'dark' : 'white'"
      :color="$vuetify.theme.dark ? 'white' : 'dark'"
    >
      <v-tab>
        概览
      </v-tab>
      <v-tab>
        添加/修改
      </v-tab>
      <v-tab>
        调试
      </v-tab>
      
      
    </v-tabs>
    <v-tabs-items v-model="tab">
      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <p>
              概览
            </p>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <p>
              概览1
            </p>
          </v-card-text>
        </v-card>
      </v-tab-item>
      <v-tab-item>
        <v-card flat>
          <v-card-text>
            <p>
              概览2
            </p>
          </v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
  </div>
</template>

<script>
  // import HelloWorld from '../components/HelloWorld'

  export default {
    name: 'Home',

    components: {
      // HelloWorld,
    },
    data: () => ({
      tab: 0
    }),
  }
</script>
