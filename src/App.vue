<template>
  <v-app style="">
    <AppNavbar :tabs.sync="tabs" :currentTab.sync= "currentTab" :currency.sync = "currency" />
    <v-main>
      <AppBody :tabs="tabs" :currentTab="currentTab" :currency = "currency" />
    </v-main>
  </v-app>
</template>

<script>
import AppNavbar from "@/components/AppNavbar";
import AppBody from "@/components/AppBody";
export default {
  name: "App",

  components: {
    AppNavbar,
    AppBody,
  },

  data: () => ({
    currency: "USD",
    currentTab: {
      id: 1,
      title: "Business Support",
      pills: "business-support",
      breadcrumb:
        "Customer Support / Telesales / Business Development / Administrators /Account Manager",
      description: [
        {
          id: 1,
          title: "Non-native non-voice Agents",
          time: "7.50 / hour",
        },
        {
          id: 2,
          title: "Non-native non-voice Agents",
          time: "7.50 / hour",
        },
        {
          id: 3,
          title: "Non-native non-voice Agents",
          time: "7.50 / hour",
        },
        {
          id: 4,
          title: "Non-native non-voice Agents",
          time: "7.50 / hour",
        },
      ],
    },
    tabs: [
      {
        id: 1,
        title: "Business Support",
        pills: "business-support",
        breadcrumb:
          "Customer Support / Telesales / Business Development / Administrators /Account Manager",
        description: [
          {
            id: 1,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
          {
            id: 2,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
          {
            id: 3,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
          {
            id: 4,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
        ],
      },
      {
        id: 2,
        title: "Design",
        pills: "design",
        breadcrumb: "Design",
        description: [
          {
            id: 5,
            title: "Graphic Design",
            time: "15 / hour",
          },
          {
            id: 6,
            title: "Illustration",
            time: "20 / hour",
          },
          {
            id: 7,
            title: "UI/UX Design",
            time: "25 / hour",
          },
          {
            id: 8,
            title: "Motion/ interaction ",
            time: "25 / hour",
          },
        ],
      },
      {
        id: 3,
        title: "Software Development",
        pills: "software-development",
        breadcrumb: "Software Development",
        description: [
          {
            id: 9,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
          {
            id: 10,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
          {
            id: 11,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
          {
            id: 12,
            title: "Non-native non-voice Agents",
            time: "7.50 / hour",
          },
        ],
      },
    ],
  }),
};
</script>

<style>
</style> 