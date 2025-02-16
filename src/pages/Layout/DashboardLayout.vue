<template>
  <div class="wrapper">
    <!-- <div class="wrapper" :class="{'nav-open': $sidebar.showSidebar}"> -->

    <side-bar :background-color="backgroundColor">
      <!-- <mobile-menu slot="content"></mobile-menu> -->

      <sidebar-link to="/dashboard">
        <i class="tim-icons icon-chart-pie-36"></i>

        <template v-if="!isRTL">
          <p>Dashboard</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/icons">
        <i class="tim-icons icon-atom"></i>

        <template v-if="!isRTL">
          <p>Icons</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/tasks">
        <i class="tim-icons icon-pin"></i>

        <template v-if="!isRTL">
          <p>Tasks</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/notifications">
        <i class="tim-icons icon-bell-55"></i>

        <template v-if="!isRTL">
          <p>Notifications</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/user">
        <i class="tim-icons icon-single-02"></i>

        <template v-if="!isRTL">
          <p>User Profile</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/table">
        <i class="tim-icons icon-puzzle-10"></i>

        <template v-if="!isRTL">
          <p>Table List</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/typography">
        <i class="tim-icons icon-align-center"></i>

        <template v-if="!isRTL">
          <p>Typography</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/dashboard?enableRTL=true">
        <i class="tim-icons icon-world"></i>

        <template v-if="!isRTL">
          <p>RTL Support</p>
        </template>
      </sidebar-link>

      <sidebar-link to="/upgradeToPro" class="active-pro">
        <i class="tim-icons icon-spaceship"></i>

        <template v-if="!isRTL">
          <p>Upgrade to PRO</p>
        </template>
      </sidebar-link>
    </side-bar>

    <div class="main-panel" :data="backgroundColor">
      <!-- 导航栏组件，用于显示在页面的顶部 -->
      <top-navbar></top-navbar>

      <!-- 仪表盘的主要内容区域 -->
      <dashboard-content @click.native="toggleSidebar"></dashboard-content>

      <!-- 页脚组件，显示在页面的底部 -->
      <content-footer></content-footer>
    </div>
  </div>
</template>

<style lang="scss"></style>

<script>
import TopNavbar from "./TopNavbar.vue";
import ContentFooter from "./ContentFooter.vue";
import DashboardContent from "./DashboardContent.vue";
import MobileMenu from "./MobileMenu.vue";
import SideBar from "@/components/SidebarPlugin/SideBar.vue";
import SidebarLink from "@/components/SidebarPlugin/SidebarLink.vue";

export default {
  components: {
    TopNavbar,
    DashboardContent,
    ContentFooter,
    // eslint-disable-next-line vue/no-unused-components
    MobileMenu,
    SideBar,
    SidebarLink,
  },
  data() {
    return {
      backgroundColor: "green",
    };
  },
  computed: {
    isRTL() {
      return this.$rtl.isRTL;
    },
  },
  methods: {
    toggleSidebar() {
      if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false);
      }
    },
  },
};
</script>
