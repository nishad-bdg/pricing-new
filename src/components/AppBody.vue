<template>
  <v-container fluid>
    <div class="header-container ml-xl-12">
      <v-row>
        <v-col
          xl="5"
          lg="6"
          md="8"
          sm="8"
          offset-xl="1"
          offset-lg="2"
          offset-md="2"
          offset-sm="1"
        >
          <v-card class="pa-sm-2 pa-2" flat color="transparent">
            <v-tabs-items v-model="tab" style="background: transparent">
              <v-tab-item>
                <div class="breadcrumb ml-sm-0 ml-1">
                  {{ currentTab.breadcrumb }}
                </div>
                <div class="progress-bar mt-4 ml-sm-0 ml-1">
                  <v-progress-linear
                    value="25"
                    background-color="#EDF2FF"
                    height="3"
                    class="custom-progressbar"
                  ></v-progress-linear>
                </div>

                <div
                  class="custom-card mt-5"
                  v-for="item in currentTab.description"
                  :key="item.id"
                >
                  <div class="card-title">
                    {{ item.title }}
                    <!-- <span class="ml-lg-4 ml-md-3 hidden-md-and-down"
                      >- {{ rateConvertion(item.rate) }} {{ item.frequency }}
                    </span> -->
                  </div>

                  <div class="d-flex flex-lg-row-reverse flex-row">
                    <div
                      class="card-title d-lg-flex d-md-none d-sm-none d-none"
                    >
                      <a href="#"> Choose Candidates </a>
                    </div>
                    <div class="mobile-eye">
                      <div class="d-flex flex-row">
                        <div class="mr-sm-10 mr-5 card-title">
                          <span>
                            - {{ rateConvertion(item.rate) }}
                            {{ item.frequency }}</span
                          >
                        </div>
                        <a
                          href="#"
                          class="d-lg-none d-md-flex d-sm-flex d-flex"
                        >
                          <img src="../assets/images/eye.svg" alt="" />
                        </a>
                      </div>
                    </div>
                  </div>
                </div>
              </v-tab-item>
            </v-tabs-items>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>
<script>
export default {
  name: "AppBody",
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
    };
  },
  methods: {
    rateConvertion(rate) {
      var usd = 1;
      var cad = 1.32;
      var gdb = 0.77;
      var aud = 1.41;
      var eur = 0.85;
      var nzd = 1.51;
      if (this.currency == "CAD") {
        return (cad * rate).toFixed(2);
      }
      if (this.currency == "GDB") {
        return (gdb * rate).toFixed(2);
      }
      if (this.currency == "AUD") {
        return (aud * rate).toFixed(2);
      }
      if (this.currency == "EUR") {
        return (eur * rate).toFixed(2);
      }
      if (this.currency == "NZD") {
        return (nzd * rate).toFixed(2);
      }
      return (usd * rate).toFixed(2);
    },
  },
};
</script>
<style scoped lang="scss">
.header-container {
  .breadcrumb {
    font-family: "Noto Sans" !important;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 19px;
    color: #d5d5d6;
  }

  .custom-progressbar {
    max-width: 550px !important;
  }
  .custom-card {
    padding: 15px;
    width: 550px;
    height: 62px;
    left: 260px;
    top: 204px;
    background: #ffffff;
    box-shadow: 0px 20px 100px rgba(0, 43, 156, 0.15);
    border-radius: 5px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    @media screen and (max-width: 767px) {
      max-width: 450px;
    }
    @media screen and (max-width: 599px) {
      width: 100%;
    }

    .card-title {
      font-family: "Noto Sans" !important;
      font-style: normal;
      font-weight: 600;
      font-size: 14px;
      line-height: 19px;
      color: #0046fe;
      @media screen and (max-width: 400px) {
        font-size: 12px;
      }

      @media screen and (max-width: 359px) {
        font-size: 8px;
      }

      span {
        color: #002178 !important;
      }
      a {
        color: #0046fe !important;
        text-transform: capitalize !important;
        text-decoration: none;
      }
    }
    .mobile-eye {
      @media screen and (max-width: 359px) {
        img {
          width: 50%;
          height: auto;
        }
      }
    }
  }
}
</style>

<style lang="scss">
.v-progress-linear__determinate.primary {
  background: #0046fe !important;
  opacity: 0.5;
}
</style>