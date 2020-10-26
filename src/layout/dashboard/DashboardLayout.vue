<template>
  <div class="wrapper">
    <side-bar>
      <template slot="links">
        <sidebar-link to="/dashboard" name="仪表盘" icon="ti-panel"/>
        <sidebar-link to="/stats" name="用户信息" icon="ti-user"/>
        <sidebar-link to="/table-list" name="列表" icon="ti-view-list-alt"/>
        <sidebar-link to="/typography" name="排版" icon="ti-text"/>
        <sidebar-link to="/icons" name="图标" icon="ti-pencil-alt2"/>
        <sidebar-link to="/maps" name="地图" icon="ti-map"/>
        <sidebar-link to="/notifications" name="警告" icon="ti-bell"/>
      </template>
      <mobile-menu>
        <li class="nav-item">
          <a class="nav-link">
            <i class="ti-panel"></i>
            <p>状态</p>
          </a>
        </li>
        <drop-down class="nav-item"
                   title="5 警告"
                   title-classes="nav-link"
                   icon="ti-bell">
          <a class="dropdown-item">警告 1</a>
          <a class="dropdown-item">警告 2</a>
          <a class="dropdown-item">警告 3</a>
          <a class="dropdown-item">警告 4</a>
          <a class="dropdown-item">其它 警告</a>
        </drop-down>
        <li class="nav-item">
          <a class="nav-link">
            <i class="ti-settings"></i>
            <p>设置</p>
          </a>
        </li>
        <li class="divider"></li>
      </mobile-menu>
    </side-bar>
    <div class="main-panel">
      <top-navbar></top-navbar>

      <dashboard-content @click.native="toggleSidebar">

      </dashboard-content>

      <content-footer></content-footer>
    </div>
  </div>
</template>
<style lang="scss">
</style>
<script>
import TopNavbar from "./TopNavbar.vue";
import ContentFooter from "./ContentFooter.vue";
import DashboardContent from "./Content.vue";
import MobileMenu from "./MobileMenu";
export default {
  components: {
    TopNavbar,
    ContentFooter,
    DashboardContent,
    MobileMenu
  },
  methods: {
    toggleSidebar() {
      if (this.$sidebar.showSidebar) {
        this.$sidebar.displaySidebar(false);
      }
    }
  }
};
</script>
