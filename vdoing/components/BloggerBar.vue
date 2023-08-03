<template>
  <aside class="blogger-wrapper card-box">
    <div class="avatar">
      <img :src="blogger.avatar" alt="头像" title="" />
    </div>
    <div class="box">
      <div class="blogger">
        <span class="name">Galileo</span>
        <span class="slogan">分享技术与生活</span>
      </div>
      <div class="icons" v-if="social && social.icons && social.icons.length">
        <a
          :key="index"
          :href="`https://github.com/GalileoFinchDudi`"
          :title="Github"
          :class="['iconfont', 'icon-github']"
          :style="{ width: 100 / social.icons.length + '%' }"
          target="_blank"
        />
        <a
          :key="index"
          :href="`https://twitter.com/Galileo_Dudu`"
          :title="Twitter"
          :class="['iconfont', 'icon-twitter']"
          :style="{ width: '10%' }"
          target="_blank"
        />
      </div>
    </div>
  </aside>
</template>

<script>
export default {
  computed: {
    blogger () {
      return this.$themeConfig.blogger
    },
    social () {
      return this.$themeConfig.social
    }
  }
}
</script>

<style lang='stylus'>
.blogger-wrapper
  height auto
  display inline-table
  padding-top 0 !important
  overflow hidden
  animation: slide-in .6s .3s backwards;
  .avatar
    width 100%
    // height 235px
    overflow hidden
    @media (max-width 900px)
      // width 205px
      // height 205px
    img
      width 100%
      height 100%
  .box
    display: flex
    flex-direction: column;
    justify-content: center;
    .icons
      // border 1px solid var(--borderColor)
      border-top none
      height 35px
      line-height 35px
      a
        font-size 20px
        width 33%
        color var(--textColor)
        display block
        float left
        text-align center
        opacity 0.8
        &:hover
          color $accentColor
    .blogger
      padding 0.3rem 0.95rem 0 0.95rem
      text-align: left;
      font-weight: 700;
      font-size: 20px;
      line-height: 1;
      margin-bottom: 5px;
      display: inline-block;
      width: 50%;
      .name
        font-size 1.3rem
        display block
        margin-bottom 6px
      .slogan
        color var(--textColor)
        font-size: 12px;
        opacity: .6;
        line-height: 1;
</style>
