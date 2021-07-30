<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-large md-dense md-primary">
        <div class="md-toolbar-row">
          <div class="md-toolbar-section-start">
            <md-button
                class="md-icon-button"
                @click="menuVisible = !menuVisible"
            >
              <md-icon>menu</md-icon>
            </md-button>

            <span class="md-title">Boise Cascade</span>
          </div>

          <md-tabs class="md-transparent" md-sync-route>
            <md-tab></md-tab>
            <md-tab id="tab-home" md-label="Home" to="/" exact></md-tab>
            <md-tab id="tab-pages" md-label="About" to="/about"></md-tab>
          </md-tabs>
        </div>
      </md-app-toolbar>

      <md-app-drawer :md-active.sync="menuVisible">
        <md-toolbar id="sideNavBar" class="md-transparent" md-elevation="0">Navigation</md-toolbar>

        <md-list class="customHover">
          <md-list-item to="/" exact>
            <md-icon>home</md-icon>
            <span class="md-list-item-text">Home</span>
          </md-list-item>

          <md-list-item to="/about">
            <md-icon>analytics</md-icon>
            <span class="md-list-item-text">About</span>
          </md-list-item>

        </md-list>
      </md-app-drawer>

      <md-app-content>
        <router-view />
      </md-app-content>
    </md-app>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component({
  computed: {}
})
export default class NavBar extends Vue {
  menuVisible = false;

}
</script>

<style lang="scss" scoped>
.md-app {
  min-height: 100vh;
  min-width: 100vh;
  border: 1px solid rgba(#000, 0.12);
  /*border: 1px solid rgba(255, 77, 166, 0.7);*/
}

.md-app-content {
  padding: 0px;
}

.md-app-toolbar {
  background-image: linear-gradient(
          to right,
          rgba(51, 51, 51, 1),
          rgba(51, 51, 51, 0.7)
  ),
  url("../../src/assets/PineTreesSnow.jpg");
}

#sideNavBar {
  background: linear-gradient(to right, rgba(51, 51, 51, 1),
      rgba(51, 51, 51, 0.7) );
  color: white;
}

// Demo purposes only
.md-drawer {
  width: 230px;
  max-width: calc(100vw - 125px);
}
.customHover {
  .md-list-item:hover {
    //background: linear-gradient(to right, rgba(66, 184, 131, 1), rgba(66, 184, 131, 0.7));
    span {
      color: rgba(66, 184, 131, 1);
    }
    .md-icon {
      color: rgba(66, 184, 131, 1) !important;
    }
  }
}

</style>
