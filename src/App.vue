<template>
  <nav>

    <div class="first-div">
      <div class="logo"><img src="@/assets/logo.svg" alt="logo"></div>

      <div>
        <router-link to="/">Model S</router-link>
        <router-link to="/">Model 3</router-link>
        <router-link to="/">Model X</router-link>
        <router-link to="/">Model Y</router-link>
        <router-view/>
      </div>

      <div>
        <h3>Shop</h3>
        <h3>Tesla Account</h3>
      </div>

      <div @click="openMenu"><i class="fa fa-bars"></i></div>

    </div>

    <div class="model-s header reveal">
      <h1>model s</h1>
      <p>Order Online for touchless delivery</p>
    </div>

    <ul v-show="menu">

      <div @click="closeMenu" class="div close">&times;</div>

      <li>Model s</li>
      <li>Model 3</li>
      <li>Model x</li>
      <li>Model y</li>
      <li>solar roof</li>
      <li>solar panel</li>
      <li>existing inventory</li>
      <li>used inventory</li>
      <li>trade-in</li>
      <li>test drive</li>
      <li>powerwall</li>
      <li>commercial energy</li>
      <li>utilities</li>
      <li>charging</li>
      <li>find us</li>
      <li>support</li>
      <li>inventor relations</li>
      <li>shop</li>
      <li>account</li>
      <li>more</li>

    </ul>

    <div class="btns">
    <button>custom orders</button>
    <button>existing inventory</button>
    </div>

  <div class="arrow-container"><i class="fa fa-angle-down"></i></div>

  </nav>

  <section class="model-y">

    <div class="header">
      <h1>model y</h1>
      <p>Order Online for touchless delivery</p>
    </div>

    <div class="btns">
    <button>custom orders</button>
    <button>existing inventory</button>
    </div>

    <div class="arrow-container"><i class="fa fa-angle-down"></i></div>

  </section>

  <section class="model-3">

    <div class="header">
      <h1>model 3</h1>
      <p>Order Online for touchless delivery</p>
    </div>

    <div class="btns">
    <button>custom orders</button>
    <button>existing inventory</button>
    </div>

    <div class="arrow-container"><i class="fa fa-angle-down"></i></div>

  </section>

  <section class="model-x">

    <div class="header reveal">
      <h1>model x</h1>
      <p>Order Online for touchless delivery</p>
    </div>

    <div class="btns">
    <button>custom orders</button>
    <button>existing inventory</button>
    </div>

    <div class="arrow-container"><i class="fa fa-angle-down"></i></div>

  </section>

  <section class="solar-panel">

    <div class="header reveal">
      <h1>solar panels</h1>
      <p>Lowest Cost Solar Panels in America</p>
    </div>

    <div class="btns">
    <button>Order now</button>
    <button>Learn more</button>
    </div>

    <div class="arrow-container"><i class="fa fa-angle-down"></i></div>

  </section>

  <section class="solar-roof">

    <div class="header reveal">
      <h1>solar roof</h1>
      <p>Produce Clean Energy From Your Roof</p>
    </div>

    <div class="btns">
    <button>Order now</button>
    <button>Learn more</button>
    </div>

    <div class="arrow-container"><i class="fa fa-angle-down"></i></div>

  </section>

  <section class="accessories">

    <div class="header reveal">
      <h1>accessories</h1>
    </div>

    <div class="btns">
    <button>Order now</button>
    </div>

  </section>

</template>

<script>
export default {
  data () {
    return {
      menu: false
    }
  },
  methods: {
    openMenu () {
      this.menu = true
    },
    closeMenu () {
      this.menu = false
    },
    addAnimation () {
      const header = document.querySelectorAll('.header')
      const btn = document.querySelectorAll('.btns')

      console.log(btn[1].getBoundingClientRect().top + ' is btn')

      for (let i = 0; i < btn.length; i++) {
        const btnTop = btn[i].getBoundingClientRect().top
        const windowHeight = window.innerHeight

        if (btnTop < windowHeight) {
          btn[i].classList.add('animate-header')
        } else {
          btn[i].classList.remove('animate-header')
        }
      }

      for (let i = 0; i < header.length; i++) {
        const headerTop = header[i].getBoundingClientRect().top
        const windowHeight = window.innerHeight

        if (headerTop < windowHeight - 100) {
          header[i].classList.add('animate-header')
        } else {
          header[i].classList.remove('animate-header')
        }
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.addAnimation)
  }
}
// alert(innerWidth)
</script>
