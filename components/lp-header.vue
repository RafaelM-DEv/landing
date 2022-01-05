<template>
  <div class="header container">
    <nav class="flex justify-between">
      <section class="flex items-center px-8 py-4">
        <img src="../assets/logo.png" alt="Logo" class="rounded-md w-[120px] h-[50px]">
      </section>

      <!-- DESKTOP -->
      <section class="hidden items-center gap-8 py-4 px-10 md:flex text-sm">
        <div>Ancora 1</div>
        <div>Ancora 2</div>
        <div>Ancora 3</div>
        <div>Ancora 4</div>
        <div>
          <button class="header__button">
            label text
          </button>
        </div>
      </section>
      <section class="flex items-center md:hidden px-10">
        <button :class="actionButton" @click="toggleMenu" />
      </section>
    </nav>

    <!-- MOBILE -->
    <nav v-if="initiate">
      <section :class="mobileMenu" class="flex-col flex justify-around items-center w-screen h-screen absolute pt-10 top-0 bg-gray-700 text-white md:hidden">
        <div class="pt-24 gap-10 flex-col flex items-center">
          <div>Ancora 1</div>
          <div>Ancora 2</div>
          <div>Ancora 3</div>
          <div>Ancora 4</div>
          <div>
            <button class="header__button">
              label text
            </button>
          </div>
        </div>
        <!-- SOCIAL-MEDIA -->
        <div class="flex text-center flex-col">
          <div class="flex gap-8 mb-8">
            <img src="https://via.placeholder.com/30x30" alt="" class="rounded-full">
            <img src="https://via.placeholder.com/30x30" alt="" class="rounded-full">
            <img src="https://via.placeholder.com/30x30" alt="" class="rounded-full">
            <img src="https://via.placeholder.com/30x30" alt="" class="rounded-full">
          </div>
          <p>@2022 Direitos Reservados</p>
        </div>
      </section>
    </nav>
  </div>
</template>

<script>
export default {

  data () {
    return {
      active: true,
      initiate: false
    }
  },

  computed: {
    actionButton () {
      return this.active ? 'header__button--close mt-3' : 'header__button--open mt-3'
    },

    mobileMenu () {
      return this.active ? 'slideOut' : 'slideIn'
    },

    initiateMode () {
      return this.initiate ? 'hidden' : ''
    }
  },

  methods: {
    toggleMenu () {
      this.initiate = true
      this.active = !this.active
      return this.active
    }
  }
}
</script>

<style lang="scss">
  .header {
    &__button {
      background-color: gray;
      padding: 8px 30px;
      border-radius: 5px;
      color: white;

      &--close {
        position: relative;
        width: 30px;
        height: 32px;
        border-top: 2px solid black;

        &::before {
          content: '';
          position: absolute;
          transition: 1s;
          top: -7px;
          left: 14px;
          border: 1px solid black;
          height: 100%;
          transform: rotate(90deg);
        }

        &::after {
          content: '';
          position: absolute;
          transition: 1s;
          top: 4px;
          left: 14px;
          border: 1px solid black;
          height: 100%;
          transform: rotate(90deg);
        }
      }

      &--open {
        position: relative;
        width: 30px;
        height: 32px;
        border-top: 0px;
        top: 0px;
        transition: 1s;
        overflow: hidden;

        &::before {
          content: '';
          transition: 1s;
          position: absolute;
          top: 0;
          left: 14px;
          border: 1px solid white;
          height: 100%;
          transform: rotate(-45deg);
        }

        &::after {
          content: '';
          transition: 1s;
          position: absolute;
          top: 0px;
          left: 14px;
          border: 1px solid white;
          height: 100%;
          transform: rotate(45deg);
        }
      }
    }
  }

  .slideIn {
    top: 0px;
    right: 0;
    z-index: -1;
    animation: slideIn 0.5s linear;
  }

  .slideOut {
    top: -100vh;
    right: 0;
    z-index: -1;
    animation: slideOut 0.5s linear;
  }

  @keyframes slideIn {
    from {
      top: -100vh;
      opacity: 0;
    }

    to {
      top: 0px;
    }
  }

  @keyframes slideOut {
    from {
      top: 0px;
    }

    to {
      opacity: 0;
      top: -100vh;
    }
  }
</style>
