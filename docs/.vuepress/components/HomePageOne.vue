<template>
  <article class="home-page-one-wrapper">
    <section class="description">
      <h1>{{ $frontmatter.heroText || $title }}</h1>
      <p class="description">{{ $description }}</p>
      <div>
        <iframe
          src="https://ghbtns.com/github-btn.html?user=oncework&repo=codeexpander&type=star&count=true&q=GitHub+Octocat+in:readme+user:defunkt"
          frameborder="0"
          scrolling="0"
          width="100px"
          height="20px"
        ></iframe>
        <a
          href="https://www.producthunt.com/posts/codeexpander?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-codeexpander"
          target="_blank"
          ><img
            src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=135763&theme=light"
            alt="CodeExpander - Type faster using abbreviations for phrases with gist. | Product Hunt Embed"
            style="width: 100px; height: 20px;"
            width="100px"
            height="20px"
        /></a>
      </div>
      <router-link class="btn-about" :to="$frontmatter.actionLink">{{
        $frontmatter.actionText
      }}</router-link>
    </section>
    <section class="md-content-wrapper">
      <Content />
    </section>
  </article>
</template>

<script>
export default {
  components: {},
  computed: {
    features() {
      return this.$frontmatter.features;
    }
  }
};
</script>

<style lang="stylus" scoped>
.img-shadow
  -webkit-filter: drop-shadow(1px 1px 4px gray);
  filter: drop-shadow(1px 1px 4px gray);
.home-page-one-wrapper
  padding-top 3.4rem
  section
    &.description
      box-sizing border-box
      margin 0 auto 1rem
      max-width 58rem
      width 100%
      text-align center
      h1
        margin-top 4rem
      p
        margin-bottom 2rem
      .btn-about
        margin 2rem 0
        display inline-block
        padding 1rem 3rem
        border-radius .25rem
        background $accentColor
        color #fff
      .banner
        display block
        width 100%
    &.wish
      overflow hidden
      &.yesterday, &.tomorrow
        background var(--code-color)
      .wish-inner
        box-sizing border-box
        margin 0 auto
        padding 2rem
        max-width 56rem
        width 100%
        min-height 25rem
        display flex
        align-items center
        > div
          flex: auto
          &.img-wrapper
            max-width 22rem
            img
              display block
              width 100%
          &.text-wrapper
            box-sizing border-box
            padding 0 2rem

@media (max-width: $MQMobile)
  .home-page-one-wrapper
    section
      padding 0 2rem
      &.description
        h1
          margin-top 5rem
      &.md-content-wrapper
        padding 0
      &.wish
        .wish-inner
          display block
          padding 2rem 0
          .img-wrapper
            margin 0 auto

@media (max-width: $MQMobileNarrow)
  .home-page-one-wrapper
    section
      padding 0 2rem
      &.description
        h1
          margin-top 5rem
      &.md-content-wrapper
        padding 0
      &.wish
        .wish-inner
          display block
          padding 2rem 0
          .img-wrapper
            margin 0 auto
</style>
