<template>
  <footer class="footer">
    <span class="scroll__top" @click="goTop" v-show="showScrollTop"></span>
    <div class="footer__top">
      <div class="container">
        <div class="footer__row">
          <div class="footer__getcall">
            <img src="img/tamasbama.png" alt="" />
            <div class="footer__getcall-info">
              <h3 class="footer__getcall-h3">تماس با ما</h3>
              <span class="gooter__getcall-span">!هر سوالی داشتید ؟ بپرسید</span>
            </div>
          </div>
          <div class="footer__info">
            <span class="footer__info-span">Email : info@domian.com</span>
            <span class="footer__info-span margin--right-10">
              Tel : 1023233030</span
            >
          </div>
        </div>
      </div>
    </div>
    <div class="footer__main">
      <div class="container">
        <div class="footer__links">
          <a href="" class="footer__link">Link 1</a>
          <a href="" class="footer__link">Link 1</a>
          <a href="" class="footer__link">Link 1</a>
          <a href="" class="footer__link">Link 1</a>
          <a href="" class="footer__link">Link 1</a>
          <a href="" class="footer__link">Link 1</a>
        </div>
        <div class="footer__hr"></div>
        <div class="footer__about">
          <p class="footer__txt">
            این فروشگاه در سال 1400 افتتاح شد و هدف آن خدمت رسانی به مشتریان است بهترین اجناس را از 
			ما بخرید با ضمانت و گارانتی
          </p>
        </div>
      </div>
      <div class="footer__team">
        design with &#x02665; by
        <a href="" class="footer__copy">اشکان مطاعی</a>
        © 2021
      </div>
    </div>
    <div class="overlay" :class="{ 'overlay--is-active': showSideBar }"></div>
  </footer>
</template>

<script>
export default {
  name: 'BaseFooter',

  props: {
    showSideBar: {
      type: Boolean,
      required: true
    }
  },

  data: () => ({
    showScrollTop: false,
    scrollTimeout: null
  }),

  methods: {
    handleScroll() {
      if (this.scrollTimeout) return

      console.log('user scrolled')

      this.scrollTimeout = setTimeout(() => {
        this.showScrollTop = window.scrollY > 200

        clearTimeout(this.scrollTimeout)
        this.scrollTimeout = 0
      }, 150)
    },
    goTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      })
    }
  },

  mounted() {
    document.addEventListener('scroll', this.handleScroll)
  },

  unmounted() {
    document.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style></style>
