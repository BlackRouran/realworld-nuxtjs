<template>
  <div>
    <!-- 头部 -->
    <nav class="navbar navbar-light">
      <div class="container">
        <!-- <a class="navbar-brand" href="index.html">conduit</a> -->
        <nuxt-link class="navbar-brand" to="/">home</nuxt-link>
        <ul class="nav navbar-nav pull-xs-right">
          <li class="nav-item">
            <nuxt-link class="nav-link" to="/" exact>home</nuxt-link>
          </li>
          <template v-if="user">
            <li class="nav-item">
              <nuxt-link class="nav-link" to="/editor">
                <i class="ion-compose"></i>&nbsp;New Post
              </nuxt-link>
            </li>
            <li class="nav-item">
              <nuxt-link class="nav-link" to="/settings"
                ><i class="ion-gear-a"></i>&nbsp;Settings</nuxt-link
              >
            </li>
            <li class="nav-item">
              <nuxt-link class="nav-link" to="/profile/123">
                <img class="user-pic" :src="user.image" />
                {{user.username}}
              </nuxt-link>
            </li>
          </template>
          <template v-else>
              <li class="nav-item">
              <nuxt-link class="nav-link" to="/login">Sign In</nuxt-link>
            </li>
            <li class="nav-item">
              <nuxt-link class="nav-link" to="/register">Sign Up</nuxt-link>
            </li>
          </template>
        </ul>
      </div>
    </nav>
    <!-- 子路由 -->
    <nuxt-child />
    <!-- 底部 -->
    <footer>
      <div class="container">
        <a href="/" class="logo-font">潘更个asdsdasdasdasdasd别</a>
        <span class="attribution">
          An interactive learning project from
          <a href="https://thinkster.io">Thinkster</a>. Code &amp; design
          licensed under MIT.
        </span>
      </div>
    </footer>
  </div>
</template>

<script>
import { mapState } from "vuex";
export default {
  name: "layoutIndex",
  computed: {
    ...mapState(["user"]),
  },
};
</script>

<style></style>
