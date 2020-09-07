<template>
  <v-app>
    <v-app-bar app class="white" z-index="1000" height="54px" elevation='1'>
      <span class="bnegra"></span>
      <div>
        <v-img
          alt="Around Logo"
          class
          contain
          src="./assets/Logo/Black.png"
          transition="scale-transition"
          width="92"
        />
      </div>

      <v-spacer></v-spacer>

      <nav class="menu_nav">
        <ul class="menu_items">
          <!-- <li v-for="(item,i) in items" :key="i" class="mr-10">{{item.title}}</li> -->

          <li class="mr-10" @click="loguear">Log In</li>
          <li class="mr-10">Community</li>
          <li class="mr-10 px-5 pys">Publish Your Space</li>
        </ul>
      </nav>

      <div class="menu hidden-sm-and-up">
        <input type="checkbox" id="check-menu" @click=" showMenu " />
        <label for="check-menu">
          <div class="icono-menu">
            <div class="barra-menu"></div>
            <div class="barra-menu"></div>
            <div class="barra-menu"></div>
          </div>
        </label>
      </div>
    </v-app-bar>

    <v-dialog v-model="logIn" max-width="414px" persistent>
      <v-card elevation="20" :class="`rounded-xl`" class="align-center d-flex flex-column pa-5">
        <v-row class="align-self-end">
          <v-btn @click="logIn = !logIn" color="gris" rounded text fab>
            <strong>X</strong>
          </v-btn>
        </v-row>
        <v-card-title>Log In</v-card-title>
        <v-card-actions class="d-flex flex-column">
          <v-btn rounded color="socialLog">
            <v-icon left class="black">mdi-light mdi-18px mdi-linkedin</v-icon>continue with LinkediN
          </v-btn>
          <v-btn rounded color="socialLog" class="my-5 btn-same">
            <v-icon left class>mdi-18px mdi-email</v-icon>
            <span class="mr-8">continue with Email</span>
          </v-btn>
        </v-card-actions>
        <v-card-text class="text-center">
          <small>
            By entering, I accept Around’s Terms &
            <br />Conditions of Use and Privacy Policy
          </small>
        </v-card-text>
      </v-card>
    </v-dialog>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    drawer: false,
    logIn: false,
    items: [
      { title: "Log In" },
      { title: "Community" },
      { title: "Publish Your Space" },
    ],
  }),
  methods: {
    showMenu() {
      const menu_items = document.querySelector(".menu_items");
      menu_items.classList.toggle("show");
    },
    loguear() {
      if (this.drawer === false) {
        const menu_items = document.querySelector(".menu_items");
        const che = document.getElementById("check-menu");
        menu_items.classList.remove("show");
        che.checked = false;
        console.log("entro");
      }
      this.logIn = !this.logIn;
    },
  },
};
</script>

<style lang='scss' scoped>

.bnegra {
  background-color: black;
  width: 26px;
  height: 26px;
  border-radius: 100%;
  margin-right: 8px;
  margin-top: 5px;
}
.menu_nav {
  @media screen and (max-width: 600px) {
    height: 54px;
  }
}
.menu_items {
  display: flex;
  list-style: none;
  margin-right: 30px;
  cursor: pointer;
  li {
    border-radius: 25px;
    margin: 0 5px;
    @media screen and (max-width: 600px) {
      line-height: 50px;
      margin-top: 10px;
    }
  }
  @media screen and (max-width: 600px) {
    position: fixed;
    width: 100%;
    height: calc(100% - 54px);
    background-color: #fff;
    top: -100vh;
    transition: all 0.8s;
    flex-direction: column;
    // align-self: start;
  }
  .pys {
     border: 1px solid black;
    border-radius: 30px;
    @media screen and (max-width: 600px) {
    border: 1px solid black;
    border-radius: 30px;
    display: inline-block;
    width: 200px;
    background-color: #000;
    color: white;
    padding: 1px 2px;
  }}
}
ul {
  left: 0;
}
ul.show {
  @media screen and (max-width: 600px) {
    top: 54px;
    right: -30px;
    background-color: #fff;
    width: 100%;
    height: 100vh;
  }
}

// menu hamburguesa animado
.menu {
  padding: 10px;
  width: 36px;
  margin-right: 15px;
  margin-top: 7px;

  height: 36px;
}
.icono-menu {
  width: 24px;
  cursor: pointer;
  overflow: hidden;
  height: 24px;
}
.barra-menu {
  width: 100%;
  height: 2.5px;
  border-radius: 0px;
  transition: 0.5s;
  background: #000;
}
.barra-menu:nth-child(1),
.barra-menu:nth-child(2) {
  margin-bottom: 3px;
}

#check-menu {
  display: none;
}
#check-menu:checked + label .main-content .main-menu {
  opacity: 1;
  height: auto;
}
#check-menu:checked + label .icono-menu .barra-menu {
  margin: 0;
}
#check-menu:checked + label .icono-menu .barra-menu:nth-child(1) {
  transform: rotate(-45deg) translate(-5px, 6.69px);
}
#check-menu:checked + label .icono-menu .barra-menu:nth-child(2) {
  transform: translate(-50px);
}
#check-menu:checked + label .icono-menu .barra-menu:nth-child(3) {
  transform: rotate(45deg) translate(3px, 1.5px);
}
</style>