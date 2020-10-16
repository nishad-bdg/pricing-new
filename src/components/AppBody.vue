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
          <v-card class="pa-2" flat color="transparent">
            <v-tabs-items v-model="tab" style="background: transparent">
              <v-tab-item>
                <div class="breadcrumb">
                  {{ currentTab.breadcrumb }}
                </div>
                <div class="progress-bar mt-4">
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
                    <span class="ml-lg-4"
                      >- {{ item.time }} {{ currency }}
                    </span>
                  </div>

                  <div class="card-title d-md-flex d-sm-none d-none">
                    Choose Candidates
                  </div>
                  <div class="mobile-eye d-md-none d-sm-flex d-flex">
                    <a href="#">
                      <img src="../assets/images/eye.svg" alt="" />
                    </a>
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

    .card-title {
      font-family: "Noto Sans" !important;
      font-style: normal;
      font-weight: 600;
      font-size: 14px;
      line-height: 19px;
      color: #0046fe;
      span {
        color: #002178 !important;
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