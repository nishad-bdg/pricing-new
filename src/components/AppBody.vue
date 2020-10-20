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
                <div class="d-flex flex-column">
                  <div v-for="i in 2" :key="i" class="mb-10">
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
                    <!-- card -->
                    <div
                      class="custom-card mt-5 d-flex flex-row"
                      v-for="item in currentTab.description"
                      :key="item.id"
                    >
                      <v-row align="center">
                        <v-col lg="5" md="6" sm="8" cols="7">
                          <div class="card-title">
                            {{ item.title }}
                          </div>
                        </v-col>
                        <v-col lg="3" md="3" class="hidden-md-and-down">
                          <div class="card-title">
                            <span>
                              - {{ rateConvertion(item.rate) }}
                              {{ item.frequency }}</span
                            >
                          </div>
                        </v-col>

                        <v-col lg="4" md="3" cols="5" align="right" offset-md="3">
                          <div class="card-title">
                            <a href="#" class="hidden-md-and-down">
                              Choose Candidates
                            </a>
                            <div
                              class="mobile-eye d-lg-none d-flex flex-row justify-space-between"
                            >
                              <div class="card-title">
                                <span>
                                  - {{ rateConvertion(item.rate) }}
                                  {{ item.frequency }}</span
                                >
                              </div>
                              <img src="../assets/images/eye.svg" alt="" />
                            </div>
                          </div>
                        </v-col>
                      </v-row>
                    </div>
                    <!-- Card -->
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
    align-items: center;
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
      font-size: 12px;
      line-height: 19px;
      color: #0046fe;
      @media screen and (max-width: 400px) {
        font-size: 12px;
      }

      @media screen and (max-width: 374px) {
        font-size: 10px;
      }

      @media screen and (max-width: 359px) {
        font-size: 9px;
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
          width: 20% !important;
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