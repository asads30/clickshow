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
        <div class="center">
          <div class="sum">100 000 000</div>
          <div class="som">so'm</div>
        </div>
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
export default {
  name: 'HomeView'
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
</style>