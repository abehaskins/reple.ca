<template>
  <div id="entry">
    <div class="meta">
      <div class="name">
        {{entry.meta.name}}
        <b class="light">
          in 4 days...
        </b>
      </div>
      <div class="duration">
        {{entry.meta.duration.from}} <b class="light">to</b> {{entry.meta.duration.to}}
      </div>
    </div>
    <div class="preview" v-bind:style="entry.style"></div>
    <div class="text">
      {{entry.meta.text}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'entry',
  props: ['entry'],
}
</script>

<style lang="scss">
#entry {
  margin-top: 10px;
  margin-bottom: 5px;
  padding-bottom: 2px;
  border-top: 1px solid #ddd;

  @media (max-width: 600px) {
    border-radius: 0px;
  }

  .meta {
    overflow: auto;
    clear: both;
    padding: 15px 10px 15px 10px;

    .name {
      float: left;
    }

    .duration {
      float: right;
    }

    .light {
      font-weight: normal;
      opacity: 0.4;
    }
  }

  .preview {
    width: 100%;
    padding: 0px;
    margin: 0px;
    height: 200px;
    background-position: center;
    background-size: cover;
  }

  .text {
    margin: 15px 15px 0px 15px;
    padding: 10px 10px 10px 15px;
    border-left: 1px dashed #ddd;
  }
}
</style>
