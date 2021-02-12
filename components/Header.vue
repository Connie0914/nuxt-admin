<template>
  <div>
    <b-navbar toggleable="lg" type="dark" style="background-color: black">
      <b-navbar-brand style="font-weight: bold" href="#">
        管理者画面
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#">ログ</b-nav-item>
          <b-nav-item href="#">アカウント管理</b-nav-item>
          <b-nav-item href="#">マスタ管理</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-item-dropdown right>
            <!-- Using 'button-content' slot -->
            <template #button-content>
              <span>ユーザー名</span>
            </template>
            <!-- <b-dropdown-item href="#">プロフィール</b-dropdown-item> -->
            <b-dropdown-item href="#">ログアウト</b-dropdown-item>
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<style>
.navbar-dark .navbar-nav .nav-link {
  color: white;
}
</style>
