<template>
  <v-app id="inspire">
    <v-app-bar app shrink-on-scroll>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <v-row>
          <v-col v-for="n in 24" :key="n" cols="4">
            <v-card :loading="loading" class="mx-auto my-12" max-width="374">
              <template slot="progress">
                <v-progress-linear
                  color="deep-purple"
                  height="10"
                  indeterminate
                ></v-progress-linear>
              </template>

              <v-img
                height="250"
                src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
              ></v-img>

              <v-card-title>room_name_placeholder</v-card-title>

              <v-card-text>

                <div class="my-4 text-subtitle-1">
                  type_placeholder
                </div>

                <div>
                  Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora sit sapiente repellendus maxime in, vitae vel aspernatur quis odio repellat veniam libero. Id at neque ab, eveniet vel quod recusandae!
                </div>
              </v-card-text>

              <v-divider class="mx-4"></v-divider>

              <v-card-actions>
                <v-btn color="deep-purple lighten-2" text @click="reserve">
                  Reserve
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
    data: () => ({
      loading: false,
      selection: 1,
    }),

    methods: {
      reserve () {
        this.loading = true

        setTimeout(() => (this.loading = false), 2000)
      },
    },
  }
</script>

<static-query>
query {
  metadata {
    siteName
  }
}

</static-query>
