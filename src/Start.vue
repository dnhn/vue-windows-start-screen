<template>
  <main id="app">
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
          borderColor: !tile.bgImage && tile.bgColor ? tile.bgColor : 'transparent',
          backgroundColor: tile.bgColor ? tile.bgColor : '#666',
          backgroundImage: tile.bgImage ? `url(${tile.bgImage})` : 'none'
        }">
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
export default {
  name: 'start',
  data () {
    return {
      tiles: [
        {
          name: 'Desktop',
          size: 'large',
          bgImage: 'https://unsplash.it/300',
        },
        {
          name: 'SkyDrive',
          size: 'medium-square',
          bgColor: 'blueviolet',
          icon: 'cloud'
        },
        {
          name: 'Maps',
          size: 'medium-square',
          bgColor: 'purple',
          icon: 'map'
        },
        {
          name: 'Photos',
          size: 'medium-square',
          bgImage: 'https://unsplash.it/200',
          icon: 'photo'
        },
        {
          name: '',
          size: 'small',
          bgColor: 'red',
          icon: 'music_video'
        },
        {
          name: '',
          size: 'small',
          bgColor: 'green',
          icon: 'camera'
        },
        {
          name: 'News',
          size: 'medium',
          bgColor: 'fuchsia',
          icon: 'announcement',
          sideBar: true
        },
        {
          name: '',
          size: 'small',
          bgColor: 'midnightblue',
          icon: 'gamepad'
        },
        {
          name: '',
          size: 'small',
          bgColor: 'darkred',
          icon: 'hearing'
        },
        {
          name: 'Calendar',
          size: 'medium',
          bgColor: 'navy',
          icon: 'calendar_today'
        },
        {
          name: 'Internet Explorer',
          size: 'medium-square',
          bgColor: 'indianred',
          icon: 'explore'
        },
        {
          name: 'Help & Tips',
          size: 'medium-square',
          bgColor: 'gold',
          icon: 'help'
        },
        {
          name: 'Food & Drink',
          size: 'medium',
          bgColor: 'grey',
          icon: 'fastfood',
          sideBar: true
        },
        {
          name: 'Mail',
          size: 'medium',
          bgColor: 'royalblue',
          icon: 'mail'
        },
        {
          name: 'Finance',
          size: 'medium',
          bgImage: 'https://unsplash.it/320',
          icon: 'show_chart'
        },
        {
          name: 'Sports',
          size: 'medium',
          bgColor: 'pink',
          icon: 'directions_run'
        },
        {
          name: 'Travel',
          size: 'medium',
          bgImage: 'https://unsplash.it/400',
          sideBar: true
        },
        {
          name: 'People',
          size: 'medium',
          bgColor: 'skyblue',
          icon: 'people'
        },
        {
          name: 'Weather',
          size: 'medium',
          bgColor: 'slategrey',
          icon: 'wb_sunny'
        },
        {
          name: 'Store',
          size: 'medium',
          bgColor: 'indigo',
          icon: 'shopping_cart'
        },
        {
          name: 'Reading List',
          size: 'medium-square',
          bgColor: 'violet',
          icon: 'local_library',
          sideBar: true
        },
        {
          name: 'Health & Fitness',
          size: 'medium-square',
          bgColor: 'green',
          icon: 'fitness_center',
          sideBar: true
        }
      ]
    }
  }
}
</script>

<style lang="scss" src="./assets/start.scss"></style>
