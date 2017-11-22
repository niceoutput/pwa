<template lang="pug">
  - var $text = "I'll be back soon"

  .canvas
    - for (i = 0; i < 40; i++)
      .parent_node
        .child_node
          .inner_child_node #{$text}
</template>


<script>
export default {

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$fontSize: 8rem;

.canvas {
  transform: rotateZ(-4deg);

  .parent_node {
    position: absolute;
    font-size: $fontSize;
    color: #fff;
    line-height: $fontSize;
    font-family: 'Bungee', cursive;
    transform: translate(-50%, -50%);
    mix-blend-mode: screen;
    letter-spacing: 0.3rem;

    @for $i from 0 through 100 {
      $key: $i + 1;
      &:nth-child(#{$key}) {
        $row: floor($i / 20);
        color: rgba(random(200) + 55, 40, random(200) + 55, 1);
        clip-path: polygon(
          $i * 5% - $row * 100% - random(2) $row * 50% - random(5),
          $key * 5% - $row * 100% + random(5) $row * 50% - random(30),
          $key * 5% - $row * 100% + random(5) $row * 50% + 50% + random(5),
          $i * 5% - $row * 100% - random(2) $row * 50% + 50% + random(30)
        );
        
        filter: blur(#{random(20) - 10}px);
        .child_node {
          animation: vertical random(1000) + 700ms random(100) + 0ms ease-in-out infinite alternate;
        }
        .inner_child_node {
          animation: horizontal random(1000) + 700ms random(100) + 0ms ease-in-out infinite alternate;
        }
      }
    }
  }
}

@keyframes horizontal {
  0% {
    transform: translateX(6px);
  }
  100% {
    transform: translateX(-6px);
  }
}
@keyframes vertical {
  0% {
    transform: translateY(3px);
  }
  100% {
    transform: translateY(-3px);
  }
}
</style>
