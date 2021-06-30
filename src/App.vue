<template>
  <v-app>
    <v-main>
      <v-app-bar :color="$vuetify.theme.dark ? 'dark' : 'white'" flat>
        <v-toolbar-title>VideoPro</v-toolbar-title>
        <v-spacer></v-spacer>
        <div v-if="$vuetify.breakpoint.name !== 'xs'">
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-btn icon v-bind="attrs" v-on="on">
                <v-icon>{{ svgPath.mdiAccount }}</v-icon>
              </v-btn>
            </template>
            <span>管理</span>
          </v-tooltip>
        </div>
        <div v-else>
          <v-btn icon>
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </div>
      </v-app-bar>
      <div class="px-3">
        <v-alert
          icon="mdi-information-outline"
          class="mb-1"
          dense
          
          type="info"
        >
          当前为Beta版本，推荐使用稳定版
        </v-alert>
      </div>
      
      <router-view/>
     
    </v-main>
  </v-app>
</template>

<script>
import { mdiAccount } from '@mdi/js'
export default {
  name: 'App',

  data: () => ({
    svgPath: {mdiAccount},
    tab: ''
  }),
};
</script>

