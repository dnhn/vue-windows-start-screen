<template>
  <main id="app" class="app">
    <transition
      appear
      name="header">
      <header>
        <h1 class="start-title">Start</h1>
        <h2 class="user-name">
          Nhan <i class="material-icons icon">person</i>
        </h2>
      </header>
    </transition>
    <transition-group
      appear
      tag="section"
      name="tile"
      class="tiles">
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
    </transition-group>
  </main>
</template>

<script>
import tilesData from './tiles-data';

export default {
  name: 'start',
  data () {
    return {
      tiles: tilesData
    }
  }
}
</script>

<style lang="scss" src="./assets/start.scss"></style>
