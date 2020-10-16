<template>
  <v-app style="width:100%;">
    <AppNavbar :tabs.sync="tabs" :currentTab.sync= "currentTab" :currency.sync = "currency" />
    <v-main>
      <AppBody :tabs="tabs" :currentTab="currentTab" :currency.sync = "currency" />
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
          rate: 7.5,
          frequency: "/ hour"
        },
        {
          id: 2,
          title: "Non-native non-voice Agents",
          rate: 7.5,
          frequency: "/ hour"
        },
        {
          id: 3,
          title: "Non-native non-voice Agents",
          rate: 7.5,
          frequency: "/ hour"
        },
        {
          id: 4,
          title: "Non-native non-voice Agents",
          rate: 7.5,
          frequency: "/ hour"
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
            rate: 7.5,
            frequency: "/ hour"
          },
          {
            id: 2,
            title: "Non-native non-voice Agents",
            rate: 7.5,
            frequency: "/ hour"
          },
          {
            id: 3,
            title: "Non-native non-voice Agents",
            rate: 7.5,
            frequency: "/ hour"
          },
          {
            id: 4,
            title: "Non-native non-voice Agents",
            rate: 7.5,
            frequency: "/ hour"
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
            rate: 15,
            frequency: "/ hour"
          },
          {
            id: 6,
            title: "Illustration",
            rate: 20,
            frequency: "/ hour"
          },
          {
            id: 7,
            title: "UI/UX Design",
            rate: 25,
            frequency:"/ hour"
          },
          {
            id: 8,
            title: "Motion/ interaction ",
            rate: 25,
            frequency:"/ hour"
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
            title: "Frontend Developer",
            rate: 35,
            frequency: "/ hour"
          },
          {
            id: 10,
            title: "Backend Developer",
            rate: 45,
            frequency: "/ hour"
          },
          
        ],
      },
    ],
  }),
};
</script>

<style>
</style> 