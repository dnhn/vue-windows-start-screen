<template>
  <main
    id="app"
    class="app"
    :class="{'app--loading': !vueMounted}">
    <header>
      <h1 class="start-title">
        Start
      </h1>
      <h2 class="user-name">
        Nhan <i class="material-icons icon">person</i>
      </h2>
    </header>
    <section class="tiles">
      <div
        class="tile"
        v-for="(tile, index) in tiles"
        :key="index"
        :class="[`tile--${tile.size}`, {'tile--sidebar': tile.sideBar}]"
        :style="{
          backgroundColor: tile.bgColor ? tile.bgColor : '#666',
          backgroundImage: tile.bgImage ? `url(${tile.bgImage})` : 'none',
          transitionDelay: `${(index * 200) + 500}ms`
        }">
        <div
          class="tile-border"
          :style="{
            borderColor: !tile.bgImage && tile.bgColor ? tile.bgColor : 'transparent'
          }">
        </div>
        <i
          class="material-icons tile-icon"
          v-if="tile.icon">
          {{tile.icon}}
        </i>
        <span class="tile-name">{{tile.name}}</span>
      </div>
    </section>
  </main>
</template>

<script>
import tilesData from './tiles-data';

export default {
  name: 'start',
  data () {
    return {
      vueMounted: false,
      tiles: tilesData
    }
  },
  mounted() {
    setTimeout(() => {
      this.vueMounted = true;
    }, 0);
  }
}
</script>

<style lang="scss" src="./assets/start.scss"></style>
