<template>
  <q-layout view="hHh LpR fFf">
    <q-header class="custom-header-transparent" style="height:0px">
      <q-toolbar>
        <nav class="navbar">
          <div class="container">
            <div class="navbar-header">
              <q-btn
                flat
                dense
                round
                icon="menu"
                aria-label="Menu"
                @click="leftDrawerOpen = !leftDrawerOpen"
                class="lt-sm"
                color="white"
              />
              <a href="#">
                <div class="text-h4 text-weight-bold">Interior</div>
              </a>
            </div>

            <div class="navbar-menu">
              <ul class="navbar-nav">
                <li exact><a href="#">Shop</a></li>
                <li><a href="#">Product</a></li>
                <li><a href="#">About</a></li>
                <li>
                  <a href="#"><q-icon size="18px" name="search"/></a>
                </li>
                <li>
                  <a href="#"
                    ><q-icon size="18px" name="fas fa-shopping-bag"
                  /></a>
                </li>
              </ul>
            </div>
          </div>
        </nav>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" bordered content-class="bg-grey-1">
      <q-list>
        <q-item-label header class="text-grey-8">
          Menu
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>


    <q-page-container>
      <router-view />
    </q-page-container>
    <footer-component></footer-component>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink.vue";
import FooterComponent from '../components/FooterComponent.vue';

const linksData = [
  {
    title: "Shop",
    link: "#shop"
  },
  {
    title: "Product",
    link: "#product"
  },
  {
    title: "About",
    link: "#about"
  }
];

export default {
  name: "MainLayout",
  components: { EssentialLink, FooterComponent },
  data() {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    };
  }
};
</script>
<style lang="scss">
.custom-header-transparent {
  position: relative;
  background-color: rgba(0, 0, 0, 0);
}

.diagonal-box {
  position: relative;
  padding: var(--skew-padding) 0;
  margin-top: -1px;

  &:before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    transform-origin: 50% 0;
    outline: 1px solid transparent;
    backface-visibility: hidden;
    z-index: -1;
  }
}

.bg-one:before {
  background-image: linear-gradient(45deg, #2161a1, #263747);
}

.bg-footer:before {
  background-image: linear-gradient(45deg, #272727, #272727);
}


@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap");

$font-family: "Roboto", sans-serif;
$font-size-base: 0.925rem;
$base-color: #FFFFFF;
$text-dark: #FFFFFF;
$border-color: #ececec;

$navbar-body-color: transparent;
$navbar-link-hover: $base-color;
$navbar-dropdown-separator-color: #eee;
$navbar-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.035);

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  font-family: $font-family;
  font-size: $font-size-base;
}

a {
  text-decoration: none;
}

// Start navbar

.navbar,
.navbar .container {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  @media (max-width: 768px) {
    display: block;
  }
  z-index: 100;
}

.navbar {
  padding: 1.15rem 1rem;
  box-shadow: $navbar-shadow;
  background-color: $navbar-body-color;

  /*
  |-----------------------------------
  | Start navbar logo or brand etc..
  |-----------------------------------
  */
  .navbar-header {
    display: flex;
    align-items: center;

    @media (max-width: 768px) {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-direction: row-reverse;
    }

    > a {
      font-weight: 500;
      color: $text-dark;
    }
  }

  /*
  |-----------------------------------
  | Start navbar menu
  |-----------------------------------
  */
  .navbar-menu {
    display: flex;
    flex-basis: auto;
    flex-grow: 1;
    align-items: center;

    @media (max-width: 768px) {
      display: none;
      text-align: center;
    }

    // Ul
    .navbar-nav {
      margin-left: auto;
      flex-direction: row;
      display: flex;
      padding-left: 0;
      margin-bottom: 0;
      list-style: none;

      @media (max-width: 768px) {
        width: 100%;
        display: block;
        border-top: 1px solid #eee;
        margin-top: 1rem;
      }

      > li {
        > a {
          color: $text-dark;
          text-decoration: none;
          display: inline-block;
          padding: 0.5rem 1rem;
          &:hover {
            color: $navbar-link-hover;
          }
          @media (max-width: 768px) {
            border-bottom: 1px solid #eee;
          }
        }
        &.active {
          a {
            color: $base-color;
          }
        }
      }

    }
  }
}

// Custom
.navbar .navbar-header > a span {
  color: $base-color;
}
.navbar .navbar-header h4 {
  font-weight: 500;
  font-size: 1.25rem;
  @media (max-width: 768px) {
    font-size: 1.05rem;
  }
}
</style>
