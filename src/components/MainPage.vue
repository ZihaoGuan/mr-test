<template>
  <main class="wrapper2">
    <img src="../assets/classic-tee.jpg" />
    <div class="detail ">
      <h1>Classic Tee</h1>
      <hr />
      <h2>$75.00</h2>
      <hr />
      <p>
        THJF Hdffd Hdffd HSJKDF FSDF HJF HSJKDHF JKAHSJKF HSJKDF FSDF HJF
        HSJKDHF Hdffd HSJKDF Hdffd HJF HSJKDHF JKAHSJKF HSJKDF FSDF HJF HSJKDHF
        JKAHSJKF HSJKDF Hdffd HJF HSJKDHF JKAHSJKF HSJKDF FSDF
      </p>

      <div class= "size-title">
        SIZE<span style="color:#C90000">*</span
        ><span id="selected-size">{{ this.size }}</span>
      </div>
      <div class="button-group">
        <button
          class="btn-size"
          :class="{ selected: this.size === 'S' }"
          @click="selectSize('S')"
        >
          S
        </button>
        <button
          class="btn-size"
          :class="{ selected: this.size === 'M' }"
          @click="selectSize('M')"
        >
          M
        </button>
        <button
          class="btn-size"
          :class="{ selected: this.size === 'L' }"
          @click="selectSize('L')"
        >
          L
        </button>
      </div>
      <button class="btn-add">ADD TO CART</button>
    </div>
  </main>
</template>

<script>
export default {
  name: "MainPage",
  data() {
    return {
      size: "",
    };
  },
  methods: {
    selectSize(size) {
      if (this.size === size) {
        this.size = "";
      } else {
        this.size = size;
      }
    },
  },
};
</script>

<style lang="sass" scoped>
main
  justify-content: space-between
  padding-top:20px
img
  height: 550px
  margin: 0 100px

.detail
  width:50%

button
  cursor: pointer
  border-radius: 0
  outline: none
  background: white

.size-title
  font-size:12px 
  padding-bottom:10px

.button-group
  padding-bottom:20px

.btn-size
  width: 3em
  height: 3em
  margin-right: 5px
  border: solid 1px rgba(0, 0, 0, 0.137)
  color: rgba(0, 0, 0, 0.137)
  &.selected
    border: solid 2px black
    color: black


.btn-add
  border: solid 2px black
  color: black
  height: 3em
  padding: 0 2em
  font-weight: bolder
  &:hover
    transition: all 0.2s ease
    color: white
    background: black

#selected-size
    font-weight: bold
    margin-left: 0.8em

@media only screen and (max-width: 768px)
  img
    margin: auto
    margin-bottom: 50px

  .detail
    width: 100%
</style>
