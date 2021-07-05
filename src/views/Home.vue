<template>
  <!-- <hello-world /> -->
  <div>
   <div class="mx-2">
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

        <v-list-item two-line>
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
        </v-list-item>

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
