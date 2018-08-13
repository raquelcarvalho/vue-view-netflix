<template>
  <div class="slider">
    <h3>{{titulo}}</h3>
    <span v-on:mouseover="scrollEsquerda()" v-on:mouseout="clearScroll()"  class="handle handlePrev active">
      <i class="fa fa-caret-left" aria-hidden="true"></i>
    </span>
    <div ref="scroller" class="row">
      <div class="row__inner">
        <Filme v-for="filme in filmes" v-bind:key="filme.id" v-bind:titulo="filme.titulo" v-bind:img="filme.img" />
      </div>
    </div>
    <span v-on:mouseover="scrollDireita()" v-on:mouseout="clearScroll()" class="handle handleNext active">
      <i class="fa fa-caret-right" aria-hidden="true"></i>
    </span>
  </div>
</template>

<script>

import Filme from './Filme'

export default {
  name: 'Categoria',
  components: {
    Filme
  },
  props: ['titulo', 'filmes'],
  data () {
    return {
      intervalo: null
    }
  },
  methods: {
    scrollDireita () {
      this.intervalo = setInterval(() => { this.$refs.scroller.scrollLeft += 1 }, 5)
    },
    scrollEsquerda () {
      this.intervalo = setInterval(() => { this.$refs.scroller.scrollLeft -= 1 }, 5)
    },
    clearScroll () {
      clearInterval(this.intervalo)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .slider {
      height: 214px;
      position: relative;
      margin: 0;
      padding: 0 4%;
      -ms-touch-action: pan-y;
      touch-action: pan-y;
  }
  .slider h3{
    position: absolute;
    top: 22px;
    z-index: 30;
  }
  .slider .handle.handlePrev {
      left: 11px;
  }
  .slider .handle.handleNext {
      right: 11px;
  }
  .slider .handle.active {
      cursor: pointer;
  }
  .slider .handle {
      background: rgba(20, 20, 20, 0.26);
      position: absolute;
      top: 0;
      height: 251px;
      bottom: 0;
      z-index: 20;
      width: 7%;
      text-align: center;
      -webkit-box-pack: center;
      -webkit-justify-content: center;
      -moz-box-pack: center;
      -ms-flex-pack: center;
      justify-content: center;
      display: -webkit-box;
      display: -webkit-flex;
      display: -moz-box;
      display: -ms-flexbox;
      display: flex;
      color: #fff;
  }
  .fa{
    font-size: 46px;
    margin-top: 120px;
  }
  .row {
    overflow: hidden;
  }
  .row__inner {
    -webkit-transition: 450ms -webkit-transform;
    transition: 450ms -webkit-transform;
    transition: 450ms transform;
    transition: 450ms transform, 450ms -webkit-transform;
    font-size: 0;
    white-space: nowrap;
    margin: 70.3125px 0;
    padding-bottom: 10px;
  }
  .row__inner:hover {
    -webkit-transform: translate3d(-62.5px, 0, 0);
            transform: translate3d(-62.5px, 0, 0);
  }
  .row__inner:hover .gui-card {
    opacity: 0.3;
  }
  .row__inner:hover .gui-card:hover {
    -webkit-transform: scale(1.5);
            transform: scale(1.5);
    opacity: 1;
  }
</style>
