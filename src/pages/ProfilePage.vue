<template>
  <div class="container">
    <div class="profile">
      <div class="profile__tabs">
        <h3 class="profile__name">Settings</h3>
        <router-link class="profile__tab" to="/profile" exact-active-class="active">
          <div class="profile__tab-img">
            <svg
              width="20"
              height="20"
              viewBox="0 0 20 20"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke="#83859C"
                d="M16.6666 17.5V15.8333C16.6666 14.9493 16.3155 14.1014 15.6903 13.4763C15.0652 12.8512 14.2174 12.5 13.3333 12.5H6.66665C5.78259 12.5 4.93474 12.8512 4.30962 13.4763C3.6845 14.1014 3.33331 14.9493 3.33331 15.8333V17.5"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <path
                d="M9.99996 9.16667C11.8409 9.16667 13.3333 7.67428 13.3333 5.83333C13.3333 3.99238 11.8409 2.5 9.99996 2.5C8.15901 2.5 6.66663 3.99238 6.66663 5.83333C6.66663 7.67428 8.15901 9.16667 9.99996 9.16667Z"
                stroke="#83859C"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
          <div class="profile__tab-content">
            <h2 class="profile__tab-title">Account</h2>
            <p class="profile__tab-text">Personal information</p>
          </div>
        </router-link>

        <router-link class="profile__tab" to="/profile/address" exact-active-class="active">
          <div class="profile__tab-img">
            <svg
              width="20"
              height="20"
              viewBox="0 0 20 20"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M17.5 8.33333C17.5 14.1667 10 19.1667 10 19.1667C10 19.1667 2.5 14.1667 2.5 8.33333C2.5 6.3442 3.29018 4.43655 4.6967 3.03003C6.10322 1.6235 8.01088 0.833328 10 0.833328C11.9891 0.833328 13.8968 1.6235 15.3033 3.03003C16.7098 4.43655 17.5 6.3442 17.5 8.33333Z"
                stroke="#83859C"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <path
                d="M10 10.8333C11.3807 10.8333 12.5 9.71404 12.5 8.33333C12.5 6.95262 11.3807 5.83333 10 5.83333C8.61929 5.83333 7.5 6.95262 7.5 8.33333C7.5 9.71404 8.61929 10.8333 10 10.8333Z"
                stroke="#83859C"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
          <div class="profile__tab-content">
            <h2 class="profile__tab-title">Address</h2>
            <p class="profile__tab-text">Shippings addresses</p>
          </div>
        </router-link>

        <router-link class="profile__tab" to="/profile/payment-methods" exact-active-class="active">
          <div class="profile__tab-img">
            <svg
              width="20"
              height="20"
              viewBox="0 0 20 20"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M17.5 3.33334H2.49998C1.5795 3.33334 0.833313 4.07953 0.833313 5V15C0.833313 15.9205 1.5795 16.6667 2.49998 16.6667H17.5C18.4205 16.6667 19.1666 15.9205 19.1666 15V5C19.1666 4.07953 18.4205 3.33334 17.5 3.33334Z"
                stroke="#83859C"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <path
                d="M0.833313 8.33334H19.1666"
                stroke="#83859C"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
          <div class="profile__tab-content">
            <h2 class="profile__tab-title">Payment method</h2>
            <p class="profile__tab-text">Connected credit cards</p>
          </div>
        </router-link>

        <router-link class="profile__tab" to="/profile/security" exact-active-class="active">
          <div class="profile__tab-img">
            <svg
              width="20"
              height="20"
              viewBox="0 0 20 20"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M9.99998 18.3333C9.99998 18.3333 16.6666 15 16.6666 10V4.16667L9.99998 1.66667L3.33331 4.16667V10C3.33331 15 9.99998 18.3333 9.99998 18.3333Z"
                stroke="#83859C"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
          <div class="profile__tab-content">
            <h2 class="profile__tab-title">Security</h2>
            <p class="profile__tab-text">Password</p>
          </div>
        </router-link>
      </div>

      <div class="account">
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations, mapGetters } from "vuex";

export default {
  name: "ProfilePage",
  data() {
    return {
      isEditing: false,
      isLoading: false,
      formData: {
        firstName: "",
        lastName: "",
        email: "",
        phoneNumber: "",
        emailNotifications: {
          newDeals: false,
          newRestaurants: false,
          orderStatuses: false,
          passwordChanges: false,
          specialOffers: false,
          newsLetter: false,
        },
      },
      errors: {
        firstName: "",
        lastName: "",
        email: "",
        phoneNumber: "",
      },
    };
  },
  computed: {
    ...mapGetters({
      userData: "user/userData",
    }),
  },
  mounted() {
    this.initPage();
  },
  methods: {
    ...mapMutations({
      logoutUser: "auth/logout",
    }),
    initPage() {
      this.formData.firstName = this.userData.firstName;
      this.formData.lastName = this.userData.lastName;
      this.formData.email = this.userData.email;
      this.formData.phoneNumber = this.userData.phoneNumber;
    },
    cancelEditing() {
      this.isEditing = false;
      this.initPage();
    },
    changeField(propertyName, value) {
      if (this.errors[propertyName] !== "") {
        this.errors[propertyName] = "";
      }

      this.formData[propertyName] = value;
      this.formData.emailNotifications[propertyName] = value;
    },
    saveChangeClick() {
      this.isLoading = true;

      setTimeout(() => {
        this.isLoading = false;
        this.isEditing = false;
      }, 2500);
    },
    logout() {
      this.logoutUser();
      this.$router.push("/");
    },
  },
};
</script>

<style lang="scss">
.profile {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 30px;

  &__name {
    font-family: $base-font;
    font-weight: 600;
    font-size: 20px;
    line-height: 28px;
    letter-spacing: 0.1px;
    margin-bottom: 16px;
    color: #2b2b43;
  }

  &__tab {
    display: flex;
    align-items: center;
    margin-bottom: 12px;
    padding: 16px;
    box-sizing: border-box;
    background: $color-white;
    border: 2px solid $color-grey-lightest;
    border-radius: 16px;

    &-img {
      background: $color-grey-lightest;
      border-radius: 12px;
      padding: 10px;
      margin-right: 12px;
      transition: all 0.15s linear;
    }

    &-title {
      font-family: $base-font;
      font-weight: 700;
      font-size: 14px;
      line-height: 20px;
      letter-spacing: 0.1px;
      color: #2b2b43;
    }

    &-text {
      font-family: $base-font;
      font-weight: 400;
      font-size: 13px;
      line-height: 18px;
      letter-spacing: 0.2px;
      color: $color-grey-dark;
    }

    &.active {
      border: 2px solid $color-primary;

      .profile {
        &__tab-img {
          background: $color-primary;
        }
      }

      path {
        stroke: $color-white;
        transition: all 0.15s linear;
      }
    }

    &:hover {
      border: 2px solid $color-primary;

      path {
        stroke: $color-white;
        transition: all 0.15s linear;
      }

      .profile {
        &__tab-img {
          background: $color-primary;
        }
      }
    }
  }
}

/* Here you can define styles how to change on mobile  */
@media screen and (max-width: 768px) {
  .profile {
    grid-template-columns: 1fr;
  }
}
</style>
