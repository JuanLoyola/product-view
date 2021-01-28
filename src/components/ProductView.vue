<template>
  <div class="container">
    <div class="container__column">
      <div class="logo">
        <img class="logo-nike" src="@/assets/nike.svg" alt="Nike Logo">
      </div>
      <div class="background"></div>
      <div class="content">
        <div class="info">
          <p class="info-name">Nike Air</p>
          <p class="info-model">Yeezy 2</p>
          <p class="info-color">Red October</p>
          <p class="info-price">$ 499.00</p>
        </div>

        <div class="cart">
          <img  class="cart-plus" src="@/assets/plus.svg" alt="plus to cart" @click="increaseValue()">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  name: 'ProductView',
  methods: {
    ...mapMutations('cart', ['increaseValue'])
  }
}
</script>

<style lang="scss" scoped>
.container {
  background-color: #FA494B;
  width: 50%;
  height: 100vh;

  &__column {
    display: flex;
    flex-flow: column nowrap;

    .logo {
      width: 68px;
      margin-top: 30px;
      margin-left: 50px;
      .logo-nike {
        width: 68px;
      }
    }

    .background {
      background-image: url('../assets/red_shoe.png');
      background-size: cover;
      display:flex;
      justify-self: center;
      margin-top: 85px;
      margin-bottom: 39px;
      width: 855px;
      height: 513px;
      cursor: pointer;
    }

    .content {
      display: flex;
      flex-flow: row nowrap;
      justify-content: space-between;
      align-items: center;

      .info {
        text-align: start;
        margin-left: 50px;
        color: #ffffff;
        font-size: 1rem;
        line-height: 29px;

        &-color {
          font-weight: 600;
        }

        &-price {
          font-weight: 600;
          font-size: 0.8rem;
          margin-top: 10px;
        }
      }

      .cart {
        margin-right: 50px;
        cursor: pointer;

        &-plus {
          width: 40px;
          height: 40px;
        }
      }
    }
  }
}
@media (min-width: 1366px) and (max-width: 1919px) {
  .container {
    max-width: 40%;
    height: 100vh;

    &__column {

      .background {
        width: 520px;
        height: 330px;
      }
    }
  }
}
@media (min-width: 1024px) and (max-width: 1365px) {
  .container {
    max-width: 40%;
    height: 100vh;

    &__column {

      .background {
        width: 350px;
        height: 230px;
      }
    }
  }
}
</style>
