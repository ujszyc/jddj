<template>
  <!--      顶部定位-->
  <div class="position">
    <span class="iconfont position__icon">&#xe619;</span>
    江苏大学互联网创新科技园1号楼10层
    <span class="iconfont position_notice">&#xe60b;</span>
  </div>
  <!--      顶部搜索-->
  <div class="search">
    <span class="iconfont">&#xe62d;</span>
    <span class="search__text">山姆会员商店优惠商品</span>
  </div>
  <!--      顶部banner-->
  <div class="banner">
    <img class="banner__img" src="../../assets/banner.jpg"/>
  </div>
  <!--      分类-->
  <div class="icons">
    <div class="icons__item" v-for="item in iconsList" :key="item.desc">
      <img
        class="icons__item__img" :src="item.imgName"/>
      <p class="icons__item__desc">{{item.desc}}</p>
    </div>
  </div>
  <!--      灰色横线-->
  <div class="gap"></div>
</template>

<script>
export default {
  name: 'StaticPart',
  setup () {
    const iconsList = [
      { imgName: require('../../assets/超市@2x.png'), desc: '超市便利' },
      { imgName: require('../../assets/菜市场@2x.png'), desc: '菜市场' },
      { imgName: require('../../assets/水果店@2x.png'), desc: '水果店' },
      { imgName: require('../../assets/鲜花@2x.png'), desc: '鲜花绿植' },
      { imgName: require('../../assets/医药健康@2x.png'), desc: '医药健康' },
      { imgName: require('../../assets/家居@2x.png'), desc: '家居时尚' },
      { imgName: require('../../assets/蛋糕@2x.png'), desc: '烘焙蛋糕' },
      { imgName: require('../../assets/签到@2x.png'), desc: '签到' },
      { imgName: require('../../assets/大牌免运@2x.png'), desc: '大牌免运' },
      { imgName: require('../../assets/红包@2x.png'), desc: '红包套餐' }
    ]
    return { iconsList }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables';
@import '../../style/mixins';
.position {
  position: relative;
  padding: .16rem .24rem .16rem 0;
  line-height: .22rem;
  font-size: .16rem;
  @include ellipsis;

  .position__icon {
    position: relative;
    top: .01rem;
    font-size: .2rem;
  }

  .position_notice {
    position: absolute;
    right: 0;
    top: .17rem;
    font-size: .2rem;
  }

  color: $content-fontcolor;
}

.search {
  margin-bottom: .12rem;
  line-height: .32rem;
  background: #F5F5F5;
  color: #B7B7B7;
  border-radius: .16rem;

  .iconfont {
    display: inline-block;
    padding: 0 .08rem 0 .16rem;
    font-size: .16rem;
  }

  &__text {
    display: inline-block;
    font-size: .14rem;
  }
}

.banner {
  height: 0;
  overflow: hidden;
  padding-bottom: 25.4%;

  &__img {
    width: 100%;
  }
}

.icons {
  display: flex;
  flex-wrap: wrap;
  margin-top: .16rem;

  &__item {
    width: 20%;

    &__img {
      display: block;
      width: .4rem;
      height: .4rem;
      margin: 0 auto;
    }

    &__desc {
      margin: .06rem 0 .16rem 0;
      text-align: center;
      color: $content-fontcolor;
    }
  }
}

.gap {
  margin: 0 -.18rem;
  height: .1rem;
  background: $content-bgColor;
}
</style>
