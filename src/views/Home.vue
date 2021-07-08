<template>
  <!-- <hello-world /> -->
  <div>
   <div class="mx-3">
      <v-card
        class="mx-auto my-5 rounded-lg"
        max-width="400"
        tile
      >
        <!-- <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Single-line item</v-list-item-title>
          </v-list-item-content>
        </v-list-item> -->

        <!-- <v-list-item two-line>
          <v-list-item-content>
            
            <v-list-item-subtitle>服务器状态</v-list-item-subtitle>
            <v-list-item-title>
              <v-badge
                dot
                inline
                left
                color="green"
              >
              <span class="pl-2">运行中</span>
            </v-badge>
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item> -->

      </v-card>

      <v-card
        class="mx-auto my-5 pa-3 rounded-0"
        max-width="400"
        tile
        elevation="0"
        style="border: 1px solid #3F6D8F;"
        color="#EEEEEE"
      >
        连接正常。
      </v-card>
    </div>
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
