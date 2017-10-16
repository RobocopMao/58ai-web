<template>
  <canvas width="200" height="80" id="logo" />
</template>

<script>
  import curvejs from 'curvejs'
  export default {
    name: 'logo',
    data () {
      return {
        stage: null
      }
    },
    mounted () {
      this.logo()
    },
    methods: {
      logo () {
        const util = {
          random: function (min, max) {
            return min + Math.floor(Math.random() * (max - min + 1))
          },
          randomColor: function () {
            return ['#22CAB3', '#90CABE', '#A6EFE8', '#C0E9ED', '#C0E9ED', '#DBD4B7', '#D4B879', '#ECCEB2', '#F2ADA6', '#FF7784'][util.random(0, 9)]
          },
          randomSpeed: function () {
            return (Math.random() > 0.5 ? 1 : -1) * Math.random() * 2
          }
        }

        const {Stage, Word, motion} = curvejs

        // let lineCount = 10,
        // random = util.random,
        // randomColor = util.randomColor,
        // randomSpeed = util.randomSpeed,
        let canvas = document.getElementById('logo')
        this.stage = new Stage(canvas)

        this.stage.add(new Word('5', {
          x: 10,
          color: util.randomColor(),
          motion: motion.dance,
          data: {angle: 0, r: 5, step: Math.PI / 50}
        }))

        this.stage.add(new Word('8', {
          x: 50,
          color: util.randomColor(),
          motion: motion.dance,
          data: {angle: 0, r: 5, step: Math.PI / 50}
        }))

        this.stage.add(new Word('a', {
          x: 90,
          color: util.randomColor(),
          motion: motion.dance,
          data: {angle: 0, r: 5, step: Math.PI / 50}
        }))

        this.stage.add(new Word('i', {
          x: 155,
          color: util.randomColor(),
          motion: motion.dance,
          data: {angle: 0, r: 5, step: Math.PI / 50}
        }))

        this.tick()
      },

      tick () {
        let vm = this
        vm.stage.update()
        requestAnimationFrame(vm.tick)
      }
    }
  }
</script>

<style lang="stylus" scoped>
  #logo {
    display block
    margin 0 auto
  }
</style>
