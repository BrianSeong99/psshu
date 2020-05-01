<template>
  <div class="wrapper">
    <parallax class="page-header header-filter" :style="headerStyle">
      <div class="md-layout">
        <div class="md-layout-item">
          <div class="image-wrapper">
            <div class="brand">
              <h1>Psshu</h1>
              <h3>Your Korean Medical Helper</h3>
            </div>
          </div>
        </div>
      </div>
    </parallax>
    <div class="main main-raised">
      <div class="profile-tabs">
        <tabs
          :tab-name="['Studio', 'Work', 'Favorite']"
          :tab-icon="['camera', 'palette', 'favorite']"
          plain
          nav-pills-icons
          color-button="success"
        >
          <!-- here you can add your content for tab-content -->
          <template slot="tab-pane-1">
            <div class="md-layout">
              <div class="md-layout-item md-size-25 ml-auto">
                <img :src="tabPane1[0].image" class="rounded" />
                <img :src="tabPane1[1].image" class="rounded" />
              </div>
              <div class="md-layout-item md-size-25 mr-auto">
                <img :src="tabPane1[3].image" class="rounded" />
                <img :src="tabPane1[2].image" class="rounded" />
              </div>
            </div>
          </template>
          <template slot="tab-pane-2">
            <div class="md-layout">
              <div class="md-layout-item md-size-25 ml-auto">
                <img :src="tabPane2[0].image" class="rounded" />
                <img :src="tabPane2[1].image" class="rounded" />
                <img :src="tabPane2[2].image" class="rounded" />
              </div>
              <div class="md-layout-item md-size-25 mr-auto">
                <img :src="tabPane2[3].image" class="rounded" />
                <img :src="tabPane2[4].image" class="rounded" />
              </div>
            </div>
          </template>
          <template slot="tab-pane-3">
            <div class="md-layout">
              <div class="md-layout-item md-size-25 ml-auto">
                <img :src="tabPane3[0].image" class="rounded" />
                <img :src="tabPane3[1].image" class="rounded" />
              </div>
              <div class="md-layout-item md-size-25 mr-auto">
                <img :src="tabPane3[2].image" class="rounded" />
                <img :src="tabPane3[3].image" class="rounded" />
                <img :src="tabPane3[4].image" class="rounded" />
              </div>
            </div>
          </template>
        </tabs>
      </div>
    </div>
  </div>
</template>

<script>
import { Tabs } from "@/components";

export default {
  components: {
    Tabs
  },
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/vue-mk-header.jpg")
    }
  },
  data() {
    return {
      firstname: null,
      email: null,
      password: null,
      tabPane1: [
        { image: require("@/assets/img/examples/studio-1.jpg") },
        { image: require("@/assets/img/examples/studio-2.jpg") },
        { image: require("@/assets/img/examples/studio-4.jpg") },
        { image: require("@/assets/img/examples/studio-5.jpg") }
      ],
      tabPane2: [
        { image: require("@/assets/img/examples/olu-eletu.jpg") },
        { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
        { image: require("@/assets/img/examples/cynthia-del-rio.jpg") },
        { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
        { image: require("@/assets/img/examples/clem-onojegaw.jpg") }
      ],
      tabPane3: [
        { image: require("@/assets/img/examples/mariya-georgieva.jpg") },
        { image: require("@/assets/img/examples/studio-3.jpg") },
        { image: require("@/assets/img/examples/clem-onojeghuo.jpg") },
        { image: require("@/assets/img/examples/olu-eletu.jpg") },
        { image: require("@/assets/img/examples/studio-1.jpg") }
      ]
    };
  },
  methods: {},
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss" scoped>
.section {
  padding: 0;
}

.profile-tabs::v-deep {
  .md-card-tabs .md-list {
    justify-content: center;
  }

  [class*="tab-pane-"] {
    margin-top: 3.213rem;
    padding-bottom: 50px;

    img {
      margin-bottom: 2.142rem;
    }
  }
}
</style>
