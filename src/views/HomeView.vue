<template>
  <div class="home page">
    <div class="container">
      <div class="home__box">
        <div class="top">
          <div class="top1">
            <div class="logo">
              <img src="@/assets/logo.svg" alt="">
            </div>
            <div class="list">
              <div class="item">забери всё</div>
              <div class="item active">топ шоу</div>
              <div class="item">o'yla</div>
            </div>
          </div>
          <div class="top2">
            <div class="list">
              <div class="item">дарим деньги</div>
              <div class="item active">click</div>
              <div class="item">sarflash</div>
              <div class="item">потратить</div>
            </div>
          </div>
        </div>
        <div class="center" v-if="amount">
          <div class="sum" v-if="amount > 0">{{ formattedNumber }}</div>
          <div class="sum" v-else>bankrot</div>
          <div class="som" v-if="amount > 0">so'm</div>
        </div>
        <div class="loader" v-else></div>
        <div class="bottom">
          <div class="bottom1">
            <div class="list">
              <div class="item">время победить</div>
              <div class="item active">imkon</div>
            </div>
          </div>
          <div class="bottom2">
            <div class="list">
              <div class="item">прайм</div>
              <div class="item">момент славы</div>
              <div class="item active">куш</div>
              <div class="item">katta o'yin</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HomeView',
  data() {
    return {
      amount: null
    }
  },
  mounted() {
    this.getBalance()
    setInterval(this.getBalance, 5000);
  },
  computed: {
    formattedNumber() {
      return this.amount.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ' ');
    },
  },
  methods: {
    getBalance(){
      axios.get('https://charity.click.uz/api/click_show/get_balance').then(res => {
        this.amount = res.data.balance
      })
    }
  },
}
</script>

<style lang="scss">
.home{
  background: #0165FF;
  &__box{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 65px 0;
    height: calc(100vh - 130px);
  }
  .top{
    display: flex;
    flex-direction: column;
  }
  .top1{
    display: flex;
    align-items: center;
    gap: 112px;
    margin-bottom: 41px;
  }
  .list{
    display: flex;
    align-items: center;
    gap: 35px;
  }
  .item{
    height: 90px;
    line-height: 90px;
    border: 5px solid #00A3FF;
    border-radius: 43px;
    padding: 0 29px;
    color: #0050CB;
    font-size: 62.85px;
    line-height: 80px;
  }
  .item.active{
    color: #fff;
    border-color: #B3FFB1;
  }
  .bottom{
    display: flex;
    flex-direction: column;
    gap: 29px;
  }
  .bottom1{
    padding-left: 37px;
  }
  .center{
    text-align: center;
    position: relative;
    .sum{
      color: #B3FFB1;
      font-size: 258.67px;
      font-weight: 700;
      text-transform: uppercase
    }
    .som{
      position: absolute;
      font-size: 103.95px;
      color: #fff;
      right: 80px;
      bottom: -50px;
    }
  }
}
@media screen and (max-width: 1700px) {
  .container{
    max-width: 1200px !important;
  }
  .home{
    &__box{
      padding: 20px 0;
      height: calc(100vh - 40px);
    }
    .top1{
      gap: 40px;
      margin-bottom: 20px;
    }
    .list{
      gap: 20px;
    }
    .item{
      height: 60px;
      line-height: 60px;
      padding: 0 15px;
      font-size: 40px;
    }
    .bottom{
      gap: 20px;
    }
    .bottom1{
      padding-left: 20px;
    }
    .center{
      .sum{
        font-size: 180px;
      }
      .som{
        font-size: 70px;
        right: 80px;
        bottom: -50px;
      }
    }
  }
}
.number {
  font-size: 24px; /* Размер шрифта */
}
.number-enter-active, .number-leave-active {
  transition: all 0.5s; /* Длительность анимации */
}
.number-enter, .number-leave-to {
  opacity: 0; /* Начальное состояние исчезновения */
  transform: translateY(-20px); /* Начальное состояние движения */
}
.loader {
  width: 50px;
  aspect-ratio: 1;
  border-radius: 50%;
  border: 8px solid;
  border-color: #fff #fff;
  animation: l1 1s infinite;
  margin: 0 auto;
}
@keyframes l1 {to{transform: rotate(.5turn)}}
</style>