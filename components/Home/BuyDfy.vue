<template>
  <client-only>
    <div class="buy-dfy">
      <div class="container">
        <v-row>
          <v-col cols="12" md="6" class="order-2 order-md-1">
            <div class="buy-dfy-with">
              <div class="buy-dfy__tabs">
                <span
                  class="buy-dfy__tabs--card tab-1"
                  :class="{'active': tab == 1}"
                  @click="tab = 1"
                >
                  <span class="tab-name">Buy DFY</span>
                  <span class="cards">
                    <img src="~assets/img/buy-dfy/visa.png" alt="">
                    <img class="img-rectangle" src="~assets/img/buy-dfy/rectangle.png" alt="">
                    <img src="~assets/img/buy-dfy/mastecard.png" alt="">
                  </span>
                </span>

                <span
                  class="buy-dfy__tabs--card"
                  :class="{'active': tab == 2}"
                  @click="tab = 2"
                >Buy DFY on Exchanges</span>
              </div>

              <div class="buy-dfy__input">
                <BuyWithCreditCard v-if="tab == 1" />
                <BuyOnExchanges v-if="tab == 2" />
              </div>
            </div>
          </v-col>

          <v-col cols="12" md="6" class="order-1 order-md-2">
            <div class="buy-dfy-img">
              <h2 class="buy-dfy__title">
                <p>
                  Buy DFY Tokens
                </p>
                <!-- <p>
                  with Credit card
                </p> -->
              </h2>
              <div class="buy-dfy__card">
                <div>
                  <img class="pr-2" src="~assets/img/buy-dfy/visa-2.png" alt="">
                  <img src="~assets/img/buy-dfy/mastecard-2.png" alt="">
                </div>
              </div>
              <div class="buy-dfy__subtext">
                <p class="text-left text-md-right mb-0">
                  Card transactions are processed by intermediaries at
                </p>
                <p class="text-left text-md-right mb-0">
                  Indacoin.com who are providers of the DFY tokens
                </p>
                <p class="text-left text-md-right">
                  through PancakeSwap Exchange.
                </p>
              </div>

              <div class="buy-dfy__img">
                <img src="~assets/img/buy-dfy/buy-dfy.png" alt="">
              </div>
            </div>
          </v-col>
        </v-row>
      </div>
    </div>
  </client-only>
</template>

<script>
import BuyOnExchanges from './BuyOnExchanges'
import BuyWithCreditCard from './BuyWithCreditCard'
export default {
  components: {
    BuyWithCreditCard,
    BuyOnExchanges
  },
  data () {
    return {
      tab: 1
    }
  }
}
</script>

<style lang="scss" scoped>
@import "~assets/components/home/_buy-dfy.scss";
</style>
