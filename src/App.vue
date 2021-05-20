<template>
  <div id="app">
    <div class="wrapper1">
      <header>
        <div class="wrapper2">
          <div id="cart" class="button-cart" :class="{show: this.hover}">
            <span
              class="button"
              @mouseover="hover = true"
              @mouseleave="hover = false"
              >My Cart ( 4 )</span
            >
            <ul class="dropdown">
              <div
                class="button"
                @mouseover="hover = true"
                @mouseleave="hover = false"           
              >
                My Cart ( 4 )
              </div>
              <li>
                <img src="./assets/classic-tee.jpg" />
                <div class="detail">
                  <div class="item-name">Classic Tee</div>
                  <div class="item-amount">1 x <span>$75.00</span></div>
                  <div class="item-size">Size: S</div>
                </div>
              </li>
              <li>
                <img src="./assets/classic-tee.jpg" />
                <div class="detail">
                  <div class="item-name">Classic Tee</div>
                  <div class="item-amount">3 x <span>$75.00</span></div>
                  <div class="item-size">Size: L</div>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </header>
      <MainPage />
    </div>
  </div>
</template>

<script>
import MainPage from "./components/MainPage.vue";

export default {
  name: "App",
  components: {
    MainPage,
  },
  data() {
    return { hover: false };
  },
  methods: {
    showCart() {
      this.hover = true;
      document.getElementById("cart").classList.add("show");
    },
    hideCart() {
      this.hover = false;
      document.getElementById("cart").classList.remove("show");
    },
  },
};
</script>

<style lang="sass">
*
  padding: 0
  margin: 0
  box-sizing: border-box

.wrapper1
  max-width: 1200px
  margin: auto

.wrapper2
  max-width: 1000px
  margin: auto
  display: flex

header
  background: #F6F6F7
  margin: 20px 0
  .wrapper2
    justify-content: flex-end

h1, h2, .font-color-1
  color:  #222222

p, .font-color-2
  color: #888888

h1
  font-size: 18px
  padding-bottom: 20px

h2
  font-size:14px
  padding: 8px 0 12px 0
  font-weight: bolder
  letter-spacing: -1px

p
  font-weight: lighter
  font-size: 12px
  padding: 20px 0
  line-height: 1.6em

hr
  border: none
  height: 0.2px
  color: rgba(0, 0, 0, 0.137)
  background-color: rgba(0, 0, 0, 0.137)

.button
  font-size:10px
  line-height:30px
  height: 30px
  padding: 0 10px
  cursor: pointer

.button-cart
  position: relative
  vertical-align: center

  &.show > ul
    visibility: visible
    display: block
    

  ul
    list-style: none
    visibility: hidden
    position: absolute
    
    right: 0
    top: 29px
    display: none
    background: white
    border:  solid 1px rgba(0, 0, 0, 0.137)
    .button
      position: absolute
      right:-1px
      top:-30px
      background: white
      border: solid 1px rgba(0, 0, 0, 0.137)
      border-bottom: none
  li
    background: white
    display: flex
    margin: 20px
    transition-duration: 0.5s
    width: 280px
    img
      height: 100px
    .detail
      margin-left:10px
      .item-name
        font-size: 14px
        padding-bottom: 5px
      .item-amount
        font-size: 14px
        padding-bottom: 5px
        span
          font-weight: bolder
          letter-spacing: -1px
      .item-size
        font-size: 12px

@media only screen and (max-width: 768px)
  .wrapper1
    width: 100%
  .wrapper2
    width: 90%
    flex-direction: column
  header
    .wrapper2
      flex-direction: row
  .button-cart
    li
      width: 80vw
  hr
    visibility: hidden
</style>
