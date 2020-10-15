<template>
  <v-container fluid ma-0 pa-0>
    <div class="app-navbar" id="app-navbar-custom">
      <div class="logo-container">
        <div class="align-center">
          <img src="../assets/images/logo.svg" alt="Logo" />
        </div>
        <!-- profile pic -->
        <v-avatar size="50">
          <v-img src="../assets/images/photo.svg"></v-img>
        </v-avatar>
        <!-- profile pic -->
      </div>

      <div class="header-container">
        <div class="header-flex">
          <div class="nav-header">Remote Talent - Price List</div>
          <div>
            <v-select
              class="currency"
              solo
              :items="currencies"
              item-text="title"
              item-value="id"
              v-model="currency"
              flat
            >
              <template v-slot:append>
                <img src="../assets/images/dropdown-arrow.svg" alt="" />
              </template>
            </v-select>
          </div>
        </div>
      </div>
    </div>
  </v-container>
</template>
<script>
export default {
  name: "AppNavbar",
  data() {
    return {
      currency: 1,
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
};
</script>
<style scoped lang="scss">
.app-navbar {
  background-color: #ffffff;
  box-shadow: 0px 0px 100px rgba(0, 0, 0, 0.05);
  min-height: 252px;
  padding: 30px;

  .logo-container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }
  .header-container {
    margin-left: 12rem;
    width: 50%;
    margin-top: 3rem;
    @media screen and (min-width: 1264px) and (max-width: 1903px) {
      width: 60%;
    }
    @media screen and (min-width: 767px) and (max-width: 959px) {
      width: 80%;
    }

    @media screen and (max-width: 959px) {
      width: 100%;
      margin-left: auto;
      margin-right: auto;
    }
    .header-flex {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
    }
    .nav-header {
      font-family: "Noto Sans" !important;
      font-style: normal;
      font-weight: 600;
      font-size: 24px;
      line-height: 33px;
      color: #405899;
    }
    .currency {
      width: 96px;
      height: 34px;
      background: #ffffff;
      box-shadow: 0px 20px 100px rgba(0, 43, 156, 0.15) !important;
      border-radius: 5px !important;
    }
  }
}
</style>

<style lang="scss">
.v-menu__content {
  margin-top: 48px !important;
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
</style>