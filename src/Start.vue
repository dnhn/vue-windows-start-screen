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
          backgroundColor: tile.bgColor ? tile.bgColor : 'transparent',
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
          bgImage: 'https://unsplash.it/360',
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
          bgImage: 'https://unsplash.it/256',
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

<style lang="scss">
.tiles {
  padding-left: 6vw;
  padding-right: 10vw;
  display: grid;
  grid-template-columns: repeat(16, 64px);
  grid-template-rows: repeat(8, 64px);
  grid-gap: 8px;
  overflow-x: auto;

  @media screen and (max-width: 1024px) {
    grid-template-columns: repeat(12, 64px);
    grid-template-rows: repeat(10, 64px);
  }

  @media screen and (max-width: 960px) {
    grid-template-columns: repeat(10, 64px);
    grid-template-rows: repeat(8, 64px);
  }

  @media screen and (max-width: 768px) {
    grid-template-columns: repeat(8, 64px);
    grid-template-rows: repeat(12, 64px);
  }

  @media screen and (max-width: 640px) {
    grid-template-columns: repeat(6, 64px);
    grid-template-rows: repeat(16, 64px);
  }

  @media screen and (max-width: 480px) {
    grid-template-columns: repeat(4, 64px);
    grid-template-rows: repeat(8, 64px);
  }
}

$tileClass: '.tile';

#{$tileClass} {
  cursor: pointer;
  position: relative;
  border-width: 3px;
  border-style: solid;
  padding: 10px;
  background-size: cover;
  background-position: center;
  color: white;
  display: flex;
  align-items: flex-end;
  font-size: 12px;

  &:hover {
    border-color: white !important;
  }

  &--small {
    grid-area: span 1 / span 1;

    #{$tileClass}-name {
      display: none;
    }
  }

  &--medium {
    grid-area: span 2 / span 4;

    #{$tileClass}-icon {
      font-size: 60px;
    }

    @media screen and (max-width: 1024px) {
      grid-area: span 2 / span 2;
    }

    @media screen and (max-width: 480px) {
      grid-area: span 1 / span 1;

      #{$tileClass}-icon {
        font-size: 30px;
      }

      #{$tileClass}-name {
        display: none;
      }
    }

    &-square {
      grid-area: span 2 / span 2;

      #{$tileClass}-icon {
        font-size: 60px;
      }

      @media screen and (max-width: 480px) {
        grid-area: span 1 / span 1;

        #{$tileClass}-icon {
          font-size: 30px;
        }

        #{$tileClass}-name {
          display: none;
        }
      }
    }
  }

  &--large {
    grid-area: span 4 / span 4;

    @media screen and (max-width: 1024px) {
      grid-area: span 2 / span 2;
    }

    @media screen and (max-width: 480px) {
      grid-area: span 1 / span 1;

      #{$tileClass}-icon {
        font-size: 30px;
      }

      #{$tileClass}-name {
        display: none;
      }
    }

    #{$tileClass}-icon {
      font-size: 120px;
    }
  }

  &-icon {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 30px;
  }

  &--sidebar {
    @media screen and (min-width: 1281px) {
      left: 4vw;
    }
  }
}
</style>
