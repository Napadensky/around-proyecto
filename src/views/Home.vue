<template >
  <v-container fluid class="px-0 overflow-hidden pt-0">
    <v-card class="rounded-b-xl" v-resize="onResize">
      <v-row justify="center">
        <v-col cols="10" lg="6" :class=" {'pl-6':!mob, 'pb-0':!mob, } ">
          <v-row justify="center">
            <v-img
              max-height=" 880 "
              min-width="280"
              src="../assets/header_hero.png"
              :class=" {'rounded-bl-xl':!mob, 'rounded-t-xl':mob, } "
            ></v-img>
          </v-row>
        </v-col>
        <v-col cols="12" lg="6" align-self="center">
          <v-row justify="center">
            <div>
              <v-banner sticky light class="white pa-0">
                <template v-slot:actions light>
                  <input type="text" placeholder="Find your Workspace" />
                  <v-icon>mdi-magnify</v-icon>
                </template>
              </v-banner>
              <v-card-actions class="d-flex"></v-card-actions>
              <v-card-title primary-title>
                <h2 :class="{'display-3':!mob, 'Founders-Approved-Wo':!mob}">
                  Founders Apporved
                  <br />Workspaces
                </h2>
              </v-card-title>
              <v-card-text>
                <p
                  :class="{'display-1':!mob, 'Unique-Workspaces-fo':!mob}"
                >Unique Workspaces for growing teams</p>
              </v-card-text>
              <v-card-actions>
                <v-btn class="gray ml-5" rounded text>
                  E
                  <span class="text-lowercase">xplore</span>
                </v-btn>
              </v-card-actions>
            </div>
          </v-row>
        </v-col>
      </v-row>
    </v-card>
    <!-- Titulo__Logos -->
    <v-row justify="center" class="mt-15">
      <v-col cols="12">
        <h2 class="text-center">We've been Around</h2>
        <!-- Img__Logos -->
        <v-row justify="center" class="mt-5">
          <v-col cols="auto" lg="3" class="pa-0" align-self="center">
            <img
              class="ma-auto"
              src="../assets/Logo/4-expansion-logo-medio-oficial_2020-09-06/4-expansion-logo-medio-oficial.png"
              alt
            />
          </v-col>
          <v-col cols="auto" lg="3" class="pa-0" align-self="center">
            <img
              src="../assets/Logo/1413842518-entrepreneur-logo_2020-09-06/1413842518-entrepreneur-logo.png"
              alt
            />
          </v-col>
          <v-col cols="auto" lg="3" class="pa-0" align-self="center">
            <img src="../assets/Logo/bitmap_2020-09-06/bitmap.png" alt />
          </v-col>

          <v-col cols="auto" lg="3" class="pa-0" align-self="center">
            <img src="../assets/Logo/bitmap_2020-09-06 (1)/bitmap.png" alt />
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Obcaecati autem ullam, consequuntur laudantium culpa officiis deleniti at molestiae? Exercitationem accusantium officia mollitia sapiente odit animi error nobis fugiat ducimus. Similique.
      Dolore deleniti, excepturi quo explicabo, quae nostrum ad distinctio suscipit aut veniam maxime corrupti doloribus perspiciatis cupiditate reiciendis sed commodi ipsum ducimus vel laudantium assumenda ipsam quos repellat. Nisi, inventore!
      Tenetur nam voluptatum similique rerum, sapiente harum quos velit impedit consectetur. Culpa dolores reprehenderit accusamus mollitia inventore maxime repudiandae qui est esse repellat eaque, dignissimos soluta sint accusantium ea fuga.
      Soluta, illo. Ullam nam corporis rem, modi voluptatum eius, incidunt odit facere eaque, ab minima praesentium. Cupiditate, laborum. Quis rem iure hic eveniet incidunt eligendi velit odio tenetur optio repudiandae.
      Odit nulla tempore incidunt veritatis, optio itaque quam delectus possimus est quo alias libero, soluta nisi. Ullam quibusdam facere fugit totam quo rerum aspernatur nisi, amet rem ex quasi mollitia.
    </p>
  </v-container>
</template>

<script>
export default {
  name: "Home",

  data() {
    return {
      mob: true,
      windowSize: {
        x: 0,
        y: 0,
      },
    };
  },
  methods: {
    onResize() {
      this.windowSize = { x: window.innerWidth, y: window.innerHeight };
      this.windowSize.x < 1270 ? (this.mob = true) : (this.mob = false);
    },
  },
};
</script>

<style lang="scss" scoped>
.Founders-Approved-Wo {
  @media (min-width: 700px) {
    font-family: HKGrotesk;
    font-size: 3.5rem;
    font-weight: 500;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.06;
    letter-spacing: -1.13px;
    color: #000000;
  }
}
.Unique-Workspaces-fo {
  @media (min-width: 700px) {
    max-width: 501px;
    height: 99px;
    font-family: HKGrotesk;
    font-size: 32px;
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.34;
    letter-spacing: -0.67px;
    color: #000000;
  }
}
img {
  @media (min-width: 995px) {
    min-width: 250px;
  }
  @media (min-width: 600px) {
    width: 150px;
  }
  @media (min-width: 100px) {
    max-width: 250px;
  }
}
</style>
