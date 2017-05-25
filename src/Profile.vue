<template>
  <div id="profile">
    <div class="top">
      <div class="background"></div>
      <div class="content">
        <div class="icon">
          <img src="https://pbs.twimg.com/profile_images/773927576184184832/HtaVmQnJ.jpg"/>
        </div>
      </div>
    </div>
    <div class="content">
      <div class="info">
        <div class="display_name">{{profile.display_name}}</div>
        <a v-bind:href="'https://twitter.com/' + profile.handle" class="handle">@{{profile.handle}}</a>
      </div>
      <div class="schedule">
        <div class="spacer">
          Upcoming Travel
        </div>
        <div class="entry" v-for="entry in upcoming_entries">
          <entry :entry="entry"></entry>
        </div>
        <div class="spacer">
          Previous Travel
        </div>
        <div class="entry" v-for="entry in previous_entries">
          <entry :entry="entry"></entry>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Entry from "./Entry.vue"

export default {
  name: 'profile',
  components: {Entry},
  data() {
    return {
      profile: {
        display_name: "Abe Haskins",
        handle: "abeisgreat"
      },
      upcoming_entries: [
        {
          meta: {
            name: "Porto, Portugal",
            duration: {
              from: "5/3",
              to: "5/5"
            },
            text: "I'll be in Porto for #memloconf this weekend!"
          },
          style:
          {
            backgroundImage: "url(https://upload.wikimedia.org/wikipedia/commons/6/62/Av_Aliados_5_%28Porto%29.jpg)"
          }
        },
        {
          meta: {
            name: "Porto, Portugal",
            duration: {
              from: "5/3",
              to: "5/5"
            },
            text: "I'll be in Porto for #memloconf this weekend!"
          },
          style:
          {
            backgroundImage: "url(https://upload.wikimedia.org/wikipedia/commons/4/48/Asamblea_Legislativa_del_Distrito_Federal_Ciudad_de_M%C3%A9xico.jpg)"
          }
        },
      ],
      previous_entries: [
        {
          meta: {
            name: "India",
            duration: {
              from: "3/3",
              to: "4/5"
            },
            text: "I'll be at #Doloconf this weekend"
          },
          style:
          {
            backgroundImage: "url(https://upload.wikimedia.org/wikipedia/commons/5/5a/Delhi_Durbar%2C_1911.jpg)"
          }
        }
      ]
    }
  }
}
</script>

<style lang="scss">
@mixin box-shadow() {
    box-shadow: 0px 2px 2px #bbb;
}

#profile {
  float: left;
  width: 100%;
  font-family: 'Montserrat', sans-serif;

  .top {
    width: 100%;
    clear: both;
    overflow: auto;
    padding-bottom: 5px;
  }

  .background {
    width: 100%;
    height: 300px;
    position: absolute;
    z-index: -1;
    background-color: #eee;
    background-image: url(https://pbs.twimg.com/profile_banners/2909811/1450641739/1500x500);
    background-position: center center;
  }

  .icon {
    background-color: white;
    margin-top: 230px;
    clear: both;
    border-radius: 3px;
    overflow: hidden;
    width: 128px;

    img {
      width: 128px;
      height: 128px;
      padding: 3px;
      border-radius: 6px;
    }

    @media (max-width: 600px) {
      margin: 230px auto 0px auto;
    }
  }

  .info {
    color: black;
    font-size: 20px;
    text-shadow: 0px 0px 2px white;
    padding: 0px 5px 6px 5px;
    clear: both;
    overflow: auto;

    @media (max-width: 600px) {
      padding: 0px 10px 5px 10px;
    }

    .display_name {
      float: left;
      padding-top: 10px;
    }

    .handle {
      color: #666;
      font-size: 16px;
      padding: 9px;
      border: 1px solid #ddd;
      border-radius: 3px;
      float: right;
      text-decoration: none;

      &:hover {
        background-color: #ddd;
      }
    }
  }

  .content {
    width: 600px;
    margin: 10px;
    margin: 0 auto;
    @media (max-width: 600px) {
      width: inherit;
      margin: 0px 0px 10px 0px;
    }
  }

  .schedule {
    .spacer {
      padding: 10px;
      margin-top: 10px;
      opacity: 0.7;
      background-color: #eee;
      border-width: 1px 0px 1px 0px;
    }
  }
}
</style>
