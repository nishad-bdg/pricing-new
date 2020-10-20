<template>
  <v-container fluid ma-0 pa-0>
    <div class="app-navbar" id="app-navbar-custom">
      <div class="logo-container">
        <div class="logo">
          <img src="../assets/images/logo.png" alt="Logo" />
        </div>
        <!-- profile pic -->
        <div class="avatar">
          <div class="badge"></div>
          <img src="../assets/images/photo.svg" />
        </div>
        <!-- profile pic -->
      </div>

      <div class="header-container ml-xl-12">
        <v-row>
          <v-col
            xl="4"
            lg="6"
            md="8"
            sm="8"
            cols="12"
            offset-xl="1"
            offset-lg="2"
            offset-md="2"
            offset-sm="1"
          >
            <div class="header-flex">
              <div class="nav-header">Remote Talent - Price List</div>
              <div>
                <v-select
                  class="currency"
                  solo
                  :items="currencies"
                  item-text="title"
                  item-value="title"
                  @change="changeCurrency"
                  v-model="currency"
                  flat
                  hide-details
                >
                  <template v-slot:append>
                    <img src="../assets/images/dropdown-arrow.svg" alt="" />
                  </template>
                </v-select>
              </div>
            </div>
            <!-- tabs -->
            <v-tabs
              background-color="transparent"
              slider-color="#0046FE"
              hide-arrows
              class="ml-xl-n4 ml-lg-n4 ml-md-n4 ml-sm-n4 ml-n5 app-tabs"
              style="position: absolute"
              v-model="tab"
            >
              <v-tab
                class="tab-text"
                active-class="tab-text-active"
                v-for="i in tabs"
                :key="i.id"
                :href="'#' + i.pills"
                @click="changeTab(i)"
                >{{ i.title }}</v-tab
              >
            </v-tabs>
            <!-- tabs -->
          </v-col>
        </v-row>
      </div>
    </div>
  </v-container>
</template>
<script>
export default {
  name: "AppNavbar",
  props: {
    tabs: {
      type: Array,
    },
    currentTab: {
      type: Object,
    },
    currency: {
      type: String,
    },
  },
  data() {
    return {
      tab: 0,
      currencies: [
        { id: 1, title: "USD" },
        { id: 2, title: "GDB" },
        { id: 3, title: "AUD" },
        { id: 4, title: "CAD" },
        { id: 5, title: "EUR" },
        { id: 6, title: "NZD" },
      ],
    };
  },
  computed: {
    // currencyList: {
    //   get: function () {
    //     return this.currencies;
    //   },
    //   set: function (value) {
    //     this.$emit("update: currency", value);
    //   },
    // },
  },
  methods: {
    changeTab(tab) {
      this.$emit("update:currentTab", tab);
    },
    changeCurrency() {
      this.$emit("update:currency", this.currency);
    },
  },
};
</script>
<style scoped lang="scss">
.app-navbar {
  max-width: 1920px !important;
  background-color: #ffffff;
  box-shadow: 0px 0px 100px rgba(0, 0, 0, 0.05);
  min-height: 250px;
  padding: 30px;

  .app-tabs {
    margin-top: 33px;
  }

  .avatar {
    img {
      width: 50px;
      height: 50px;
      border-radius: 100px !important;
    }
  }
  .badge {
    position: absolute;
    width: 10px;
    height: 10px;
    border-radius: 100%;
    background: #42b72a;
    z-index: 1006;
    margin-left: 37px;
  }

  .logo-container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    .logo img {
      width: 171px;
      height: 32px;
    }
  }
  .header-container {
    margin-top: 36px;
    .header-flex {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
    }
    .nav-header {
      font-family: "Noto Sans" !important;
      font-style: normal;
      font-weight: 600;
      font-size: 24px;
      line-height: 33px;
      color: #405899;
      @media screen and (max-width: 959px) {
        font-size: 18px;
        line-height: 24.52px;
      }
      @media screen and (max-width: 400px) {
        font-size: 14px;
      }
      @media screen and (max-width: 350px) {
        font-size: 12px;
      }
    }
    .currency {
      width: 96px;
      height: 34px;
      background: #ffffff;
      box-shadow: 0px 20px 100px rgba(0, 43, 156, 0.15) !important;
      border-radius: 5px !important;
    }
    .tab-text {
      font-family: "Noto Sans" !important;
      font-style: normal;
      font-weight: 500 !important;
      font-size: 16px;
      line-height: 22px;
      color: #d5d5d6 !important;
      text-transform: capitalize;
      margin-top: -20px;
      @media screen and (max-width: 1263px) {
        font-size: 14px;
        line-height: 19.07px;
      }
    }
    .tab-text-active {
      font-family: "Noto Sans" !important;
      font-style: normal;
      font-weight: 500 !important;
      font-size: 16px;
      line-height: 22px;
      color: #0046fe !important;
      text-transform: capitalize;
      @media screen and (max-width: 1263px) {
        font-size: 14px;
        line-height: 19.07px;
      }
    }
  }
}
</style>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans&display=swap");
.v-menu__content {
  margin-top: 34px !important;
  background: #ffffff;
  box-shadow: 0px 20px 100px rgba(0, 43, 156, 0.15) !important;
  border-radius: 0px 0px 5px 5px !important;
}
.v-list-item__title {
  font-family: "Noto Sans" !important;
  font-style: normal;
  font-weight: 500;
  font-size: 12px !important;
  line-height: 16px;
  color: #0046fe;
}
.v-text-field.v-text-field--solo .v-input__control {
  min-height: 34px !important;
}
.v-tabs-slider {
  min-height: 4px !important;
  border-radius: 10px 10px 0px 0px !important;
  width: 50% !important;
  margin-top: -2px;
  margin-left: 15px;
}
.theme--light.v-select .v-select__selection--comma {
  font-family: "Noto Sans" !important;
  font-style: normal;
  font-weight: 500;
  font-size: 14px !important;
  line-height: 16px;
  color: #0046fe !important;
}
.v-slide-group__prev--disabled {
  display: none !important;
}
.v-list-item {
  min-height: 30px !important;
  max-height: 20px !important;
}
</style>