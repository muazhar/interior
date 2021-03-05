<template>
  <div class="diagonal-box bg-footer">
    <footer class="site-footer ">
      <div class="process-section container q-pb-md">
        <div class="row">
          <div class="q-pa-md col-xs-6 col-sm-6 col-md-3">
            <h6 class="text-white">Contact Us</h6>
            <ul class="footer-links">
              <li><a href="#/about">info@interior.com</a></li>
              <li><a href="#/about">www.interior.com</a></li>
              <li><a href="#/about">+92909098987</a></li>
            </ul>
          </div>

          <div class="q-pa-md col-xs-6 col-sm-6 col-md-3">
            <h6 class="text-white">Quick Links</h6>
            <ul class="footer-links">
              <li><a href="#">About</a></li>
              <li><a href="#">Products</a></li>
              <li><a href="#">Shop</a></li>
            </ul>
          </div>

          <div class="q-pa-md col-xs-6 col-sm-6 col-md-3">
            <h6 class="text-white">Do you have a question</h6>

            <q-input
              color="dark"
              outlined
              bg-color="white"
              v-model="text"
              placeholder="Enter email address"
            >
              <template v-slot:append>
                <q-btn color="primary" no-caps  label="Send" @click="onClick" />
              </template>
            </q-input>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      email: "info@interior.com"
    };
  }
};
</script>
<style lang="scss">
.site-footer {
  padding: 45px 0 0px;
  font-size: 15px;
  line-height: 20px;
}
.site-footer hr {
  border-top-color: $dark;
  opacity: 0.5;
}
.site-footer hr.small {
  margin: 20px 0;
}
.site-footer h6 {
  font-size: 16px;
  text-transform: uppercase;
  margin-top: 5px;
  letter-spacing: 2px;
  padding: 0px 0px 30px 0px;
}
.site-footer a {
  color: #fff;
  text-decoration: none;
}
.site-footer a:hover {
  color: #fff;
}
.footer-links {
  padding-left: 0;
  list-style: none;
}
.footer-links li {
  display: block;
  margin: 0 0 10px 0px;
}
.footer-links a {
  color: #fff;
}
.footer-links a:active,
.footer-links a:focus,
.footer-links a:hover {
  color: #fff;
  text-decoration: underline;
}
.footer-links.inline li {
  display: inline-block;
}
.site-footer .social-icons {
  text-align: right;
}
.site-footer .social-icons a {
  width: 40px;
  height: 40px;
  line-height: 40px;
  margin-left: 6px;
  margin-right: 0;
  border-radius: 100%;
  background-color: #fff;
}
.copyright-text {
  margin: 0;
}
@media (max-width: 991px) {
  .site-footer [class^="col-"] {
    margin-bottom: 30px;
  }
}
@media (max-width: 767px) {
  .site-footer {
    padding-bottom: 0;
  }
  .site-footer .copyright-text,
  .site-footer .social-icons {
    text-align: center;
  }
}

.social-buttons {
  display: flex;
  flex-wrap: wrap;

  &__button {
    margin: 0px 2px 0;
  }
}

$social-button-radius: 35px;
$social-button-icon-size: 0.5;
$social-button-background: #21252a;
$social-button-active-color: #fff;
$social-button-transition-time: 0.3s;

$social-button-colors: (
  "facebook": #4867aa,
  "linkedin": #50abf1,
  "snapchat": #fe0000
);

.social-button {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  outline: none;
  width: $social-button-radius;
  height: $social-button-radius;
  text-decoration: none;
  &__inner {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: calc(100% - 2px);
    height: calc(100% - 2px);
    border-radius: 100%;
    text-align: center;
    color: white;
  }

  i,
  svg {
    position: relative;
    z-index: 1;
    transition: $social-button-transition-time;
  }

  i {
    font-size: $social-button-radius * $social-button-icon-size;
  }

  svg {
    height: percentage($social-button-icon-size);
    width: percentage($social-button-icon-size);
  }

  &::after {
    content: "";
    position: absolute;
    top: 0;
    left: 50%;
    display: block;
    width: 0;
    height: 0;
    border-radius: 100%;
    transition: $social-button-transition-time;
  }

  &:focus,
  &:hover {
    color: $social-button-active-color;
    &::after {
      width: 100%;
      height: 100%;
      margin-left: -50%;
    }
  }

  @each $name, $color in $social-button-colors {
    &--#{$name} {
      background: $color;

      &::after {
        background: $color;
      }
    }
  }
}
</style>
