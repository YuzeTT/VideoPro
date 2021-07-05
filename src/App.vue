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
                <v-icon>{{ svgPath.mdiEqualizer }}</v-icon>
              </v-btn>
            </template>
            <span>概览</span>
          </v-tooltip>
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-btn icon v-bind="attrs" v-on="on">
                <v-icon>{{ svgPath.mdiDatabaseEdit }}</v-icon>
              </v-btn>
            </template>
            <span>编辑</span>
          </v-tooltip>
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
          
          :type="alert.type"
        >
          {{ alert.text }}
        </v-alert>
      </div>
      
      <router-view/>
      <v-btn @click="info()">Axios</v-btn>
      <div>{{axios_info}}</div>
    </v-main>
  </v-app>
</template>

<script>
import { 
  mdiAccount,
  mdiEqualizer,
  mdiDatabaseEdit,
} from '@mdi/js'
import axios from 'axios'
export default {
  name: 'App',

  data: () => ({
    svgPath: {
      mdiAccount,
      mdiEqualizer,
      mdiDatabaseEdit,
    },
    alert: {
      type: 'info',
      text: '正在连接中...',
    },
    tab: '',
    axios_info: ''
  }),
  mounted () {
    axios
      .get('http://192.168.2.179:2048/status')
      .then(response => {
        if (response.data.status == 200) {
          this.alert.type = 'success'
          this.alert.text = '连接服务器成功'
        }
      })
      .catch(error => {
        console.log(error)
        this.alert.type = 'error'
        this.alert.text = '[本地浏览] 无法连接到服务器，请检查网络并刷新重试。' + error
      })
  },
  methods: {
    info: function() {
      axios
        .get('http://192.168.2.179:2048/status')
        .then(response => (this.axios_info = response))
      console.log(this.axios_info)
    }
  }
};
</script>

