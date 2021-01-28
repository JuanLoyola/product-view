<template>
  <div class="container">
    <div class="nav">
      <div class="arrow">
        <img src="@/assets/seta-esquerda.svg" alt="arrow" class="arrow-back">
      </div>
      <div class="title">
        <p>Most <br> <strong>Popular</strong></p>
      </div>

      <div class="cart">
        <p>CART({{currentValue || 0}})</p>
      </div>
    </div>

    <div class="row">

      <div class="card" v-for="(item, index) in cards.info[0].variants" :key="index">

      <div class="imgBox">
        <img class="sneaker" :src="item.image" alt="sneaker">
      </div>

      <div class="content">
        <p class="content-name">Nike Air Yeezy 2</p>
        <p class="content-model">Red October</p>
        <p class="content-price">$ 499.00</p>
      </div>

      <div class="more">
        <div class="view">
          <p>View</p>
        </div>
        <div class="options">
          <p>...</p>
        </div>
      </div>

    </div>

    </div>

      <footer class="lastInfo">
        <p>Popular</p>
        <p>New Arrivals</p>
        <p>Categories</p>
      </footer>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'ProductCards',
  data () {
    return {
      cards: {
        info: [
          {
            variants: [
              {
                image: 'https://i.imgur.com/B0d6xhI.jpg'
              },
              {
                image: 'https://i.imgur.com/OEqj8LX.png'
              },
              {
                image: 'https://i.imgur.com/tFdEvDU.png'
              }
            ]
          }
        ]
      }
    }
  },
  computed: {
    ...mapState('cart', ['currentValue'])
  }
}
</script>

<style lang="scss" scoped>
.container{
  width: 50%;
  height: 100vh;

  .nav {
    width: 100%;
    display: flex;
    flex-flow: row nowrap;
    font-size: 1.3rem;
    margin-top: 40px;

    .arrow {
      margin: 0 50px;
        &-back {
        width: 50px;
      }
    }

    .cart {
      justify-self: flex-end;
      font-weight: 300;
      width: 100%;
    }
  }

  .row {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;

    .card {
      width: 230px;
      height: 390px;
      box-shadow: 0px 4px 35px rgba(0, 0, 0, 0.3);
      border-radius: 9px;
      cursor: pointer;
      margin: 90px 20px;

      .imgBox {
        padding-top: 47px;
        margin-bottom: 44px;

        .sneaker {
          width: 230px;
          height: 147px;
        }
      }

      .content {
        text-align: start;
        line-height: 22px;
        margin-left: 20px;
        margin-bottom: 20px;

        &-model {
          font-weight: 600;
        }

        &-price {
          margin-top: 10px;
          font-weight: 500;
        }
      }

      .more {
        font-size: 1rem;
        color: #afaeae;
        display: flex;
        flex-flow: row nowrap;
        justify-content: space-between;
        align-items: center;
        margin: 0 20px 0 20px;

        .options {
          font-size: 22px;
        }
      }
    }
  }

  .lastInfo {
    width: 50%;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-around;
    cursor: pointer;
    font-weight: 500;
  }
}
@media (min-width: 1024px) and (max-width: 1365px) {
  .container{
    width: auto;
    height: 100vh;

    .row {
      margin-left: 10px;

      .card {
        width: 190px;
        height: 390px;
        margin: 90px 10px;

        .imgBox {

          .sneaker {
            width: 190px;
            height: 130px;
          }
        }
      }
    }
  }
}

@media (min-width: 1366px) and (max-width: 1919px){
  .container{
    width: auto;
    height: 100vh;

    .row {
      margin-left: 10px;

      .card {
        width: 190px;
        height: 390px;
        margin: 90px 10px;

        .imgBox {

          .sneaker {
            width: 190px;
            height: 130px;
          }
        }
      }
    }
  }
}

</style>
