<template>
  <div class="-scroll">
    <div class="page1">
      <div class="logo">
        <form id="form" @submit.prevent="doEnterRoom">
          <a @click.prevent="doEnterRoom" :href="url" id="link" class="link"
            >Brie<span class="dot">.</span>fi<span class="slash">/</span>ng<span
              class="slash"
              >/</span
            ></a
          >
          <wbr />
          <input
            type="text"
            id="room"
            name="room"
            ref="input"
            enterkeyhint="go"
            spellcheck="false"
            v-model="room"
            :placeholder="defaultName"
          />
        </form>
        <div class="button-container">
          <a
            @click.prevent="doEnterRoom"
            :href="url"
            class="button start-button"
            id="button"
            >{{ l.welcome.start }}</a
          >
        </div>
      </div>
      <div class="footer links">
        <p>
          {{ l.welcome.abstract }}

          <a
            href="#help"
            onclick="document.getElementById('help').scrollIntoView({behavior: 'smooth'}); return false;"
            >{{ l.welcome.help }}</a
          >
        </p>
        <p>
          {{ l.welcome.created }}
          <a
            href="https://chatlink.in"
            target="_blank"
            rel="noopener"
            @click="openExternalLink"
            >Chat Link</a
          >
          <a
            title="Follow @chatlink on Twitter"
            href="https://twitter.com/user_name"
            class="brand-icon"
            target="_blank"
            rel="noopener"
            @click="openExternalLink"
          >
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M23.954 4.569c-.885.389-1.83.654-2.825.775 1.014-.611 1.794-1.574 2.163-2.723-.951.555-2.005.959-3.127 1.184-.896-.959-2.173-1.559-3.591-1.559-2.717 0-4.92 2.203-4.92 4.917 0 .39.045.765.127 1.124C7.691 8.094 4.066 6.13 1.64 3.161c-.427.722-.666 1.561-.666 2.475 0 1.71.87 3.213 2.188 4.096-.807-.026-1.566-.248-2.228-.616v.061c0 2.385 1.693 4.374 3.946 4.827-.413.111-.849.171-1.296.171-.314 0-.615-.03-.916-.086.631 1.953 2.445 3.377 4.604 3.417-1.68 1.319-3.809 2.105-6.102 2.105-.39 0-.779-.023-1.17-.067 2.189 1.394 4.768 2.209 7.557 2.209 9.054 0 13.999-7.496 13.999-13.986 0-.209 0-.42-.015-.63.961-.689 1.8-1.56 2.46-2.548l-.047-.02z"
              />
            </svg>
          </a>
          <a
            title="Follow ChatLink on LinkedIn"
            href="https://linkedin.com/user_name"
            class="brand-icon"
            target="_blank"
            rel="noopener"
            @click="openExternalLink"
          >
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
              />
            </svg>
          </a>
          <a
            title="Follow ChatLink on Facebook"
            href="https://facebook.com/yourpage/"
            class="brand-icon"
            target="_blank"
            rel="noopener"
            @click="openExternalLink"
          >
            <svg viewBox="0 0 320 512" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"
              />
            </svg>
          </a>
          <a
            title="Android App"
            href="https://play.google.com/store/apps/details?id=com.pb.rumble"
            class="brand-icon"
            target="_blank"
            rel="noopener"
            @click="openExternalLink"
          >
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M 7.703125 18.820312 C 7.703125 22.902344 10.949219 26.207031 14.960938 26.207031 C 18.972656 26.207031 22.21875 22.902344 22.21875 18.820312 L 22.21875 14.601562 L 7.703125 14.601562 Z M 19.234375 6.550781 L 21.410156 4.332031 L 20.5625 3.457031 L 18.175781 5.894531 C 17.203125 5.398438 16.125 5.105469 14.960938 5.105469 C 13.800781 5.105469 12.722656 5.398438 11.757812 5.894531 L 9.363281 3.457031 L 8.511719 4.332031 L 10.691406 6.550781 C 8.886719 7.890625 7.703125 10.042969 7.703125 12.488281 L 7.703125 13.542969 L 22.21875 13.542969 L 22.21875 12.488281 C 22.21875 10.042969 21.039062 7.890625 19.234375 6.550781 Z M 11.851562 11.433594 C 11.28125 11.433594 10.8125 10.960938 10.8125 10.378906 C 10.8125 9.800781 11.28125 9.324219 11.851562 9.324219 C 12.421875 9.324219 12.886719 9.800781 12.886719 10.378906 C 12.886719 10.960938 12.421875 11.433594 11.851562 11.433594 Z M 18.074219 11.433594 C 17.503906 11.433594 17.035156 10.960938 17.035156 10.378906 C 17.035156 9.800781 17.503906 9.324219 18.074219 9.324219 C 18.644531 9.324219 19.109375 9.800781 19.109375 10.378906 C 19.109375 10.960938 18.644531 11.433594 18.074219 11.433594 Z M 18.074219 11.433594 "
              />
            </svg>
          </a>
          <a
            title="Microsoft Windows App Store"
            href="#"
            class="brand-icon"
            target="_blank"
            rel="noopener"
            @click="openExternalLink"
          >
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M0 3.449L9.75 2.1v9.451H0m10.949-9.602L24 0v11.4H10.949M0 12.6h9.75v9.451L0 20.699M10.949 12.6H24V24l-12.9-1.801"
              />
            </svg>
          </a>
          <a
            title="iOS App"
            href="#"
            class="brand-icon"
            target="_blank"
            rel="noopener"
            @click="openExternalLink"
          >
            <svg id="apple" viewBox="0 0 24 24">
              <path
                d="M7.078 23.55c-.473-.316-.893-.703-1.244-1.15-.383-.463-.738-.95-1.064-1.454-.766-1.12-1.365-2.345-1.78-3.636-.5-1.502-.743-2.94-.743-4.347 0-1.57.34-2.94 1.002-4.09.49-.9 1.22-1.653 2.1-2.182.85-.53 1.84-.82 2.84-.84.35 0 .73.05 1.13.15.29.08.64.21 1.07.37.55.21.85.34.95.37.32.12.59.17.8.17.16 0 .39-.05.645-.13.145-.05.42-.14.81-.31.386-.14.692-.26.935-.35.37-.11.728-.21 1.05-.26.39-.06.777-.08 1.148-.05.71.05 1.36.2 1.94.42 1.02.41 1.843 1.05 2.457 1.96-.26.16-.5.346-.725.55-.487.43-.9.94-1.23 1.505-.43.77-.65 1.64-.644 2.52.015 1.083.29 2.035.84 2.86.387.6.904 1.114 1.534 1.536.31.21.582.355.84.45-.12.375-.252.74-.405 1.1-.347.807-.76 1.58-1.25 2.31-.432.63-.772 1.1-1.03 1.41-.402.48-.79.84-1.18 1.097-.43.285-.935.436-1.452.436-.35.015-.7-.03-1.034-.127-.29-.095-.576-.202-.856-.323-.293-.134-.596-.248-.905-.34-.38-.1-.77-.148-1.164-.147-.4 0-.79.05-1.16.145-.31.088-.61.196-.907.325-.42.175-.695.29-.855.34-.324.096-.656.154-.99.175-.52 0-1.004-.15-1.486-.45zm6.854-18.46c-.68.34-1.326.484-1.973.436-.1-.646 0-1.31.27-2.037.24-.62.56-1.18 1-1.68.46-.52 1.01-.95 1.63-1.26.66-.34 1.29-.52 1.89-.55.08.68 0 1.35-.25 2.07-.228.64-.568 1.23-1 1.76-.435.52-.975.95-1.586 1.26z"
              />
            </svg>
          </a>
        </p>
      </div>
    </div>
    <app-help></app-help>
  </div>
</template>

<style lang="scss">
.page1 {
  text-align: center;
  flex-shrink: 0;
  height: 100%;
  display: flex;
  flex-direction: column;
  line-height: 1.5;

  /*.text {*/
  /*  max-width: 40rem;*/
  /*  margin-left: auto;*/
  /*  margin-right: auto;*/
  /*  text-align: left;*/
  /*  padding: 1rem;*/
  /*  margin-top: 4rem;*/
  /*}*/

  a {
    color: inherit;
    text-decoration: inherit;
  }

  .logo {
    flex: auto;
    flex-direction: column;
    justify-content: center;
    display: inline-flex;
    align-items: center;
    font-variant-ligatures: common-ligatures;
    padding: 1rem;
    padding-top: 5rem;
    font-size: 4rem;
  }

  .dot,
  .slash {
    color: #00b5ff;
    opacity: 0.8;
  }

  .button-container {
    margin-top: 2rem;
  }

  .button {
    border: none;
    background: #00a2e4;
    color: white;
    font-weight: 400;
    font-size: 2rem;
    border-radius: 0.25rem;
    padding: 1rem 1.5rem;
    text-decoration: none;

    &:hover {
      background: #00b5ff;
    }

    &:active {
      background: #0088c0;
    }
  }

  .footer {
    margin-top: 5rem;
    opacity: 0.6;
    padding: 1rem;

    a {
      color: #00b5ff;
      text-decoration: none;
    }

    a:hover {
      color: rgba(129, 228, 255, 1);
    }

    a:active {
      color: #0088c0;
    }
  }

  /*.text a {*/
  /*  color: #0088c0;*/
  /*  text-decoration: none;*/

  /*  a:hover {*/
  /*    color: #00b5ff;*/
  /*  }*/

  /*  a:active {*/
  /*    color: #99e2ff;*/
  /*  }*/
  /*}*/

  input,
  input::placeholder {
    appearance: none;
    border: none;
    background: transparent;
    color: #99e2ff !important;
    font-size: inherit;
  }

  input {
    max-width: 90vw !important;
    width: 1px;
    padding: 0;
    margin: 0;
    outline: 0;
  }

  input::placeholder {
    opacity: 0.5;
  }

  @media only screen and (max-width: 799px) {
    .logo {
      font-size: 8vw;
    }

    .link {
      font-size: 12vw;
      display: block;
    }

    .button-container {
      /*margin-top: 4vw;*/
      margin-top: 4rem;
    }

    .button {
      font-size: 4vw;
    }
  }

  .brand-icon {
    margin-left: 0.5rem;
    display: inline-block;
    vertical-align: middle;

    svg {
      fill: currentColor;
      color: inherit;
      width: 1rem; //  auto !important;
      height: 1rem;
    }
  }
}
</style>

<script>
import { DEBUG, ROOM_PATH } from "../config"
import AppHelp from "./app-help"
import { trackSilentException } from "../bugs"
import { generateName } from "../lib/names"

export default {
  name: "app-welcome",
  components: {
    AppHelp,
  },
  data() {
    let defaultName = DEBUG
      ? process.env.VUE_APP_DEBUG_DEFAULT_ROOM || "development"
      : generateName()
    return {
      defaultName,
      room: defaultName,
      url: "",
      initialWidth: -1,
      currentChar: 0,
      observer: null,
    }
  },
  methods: {
    doEnterRoom() {
      const room = this.room || this.defaultName || ""
      this.state.room = room
      try {
        window.history.pushState(
          null, // { room },
          null, // room,
          ROOM_PATH + room
        )
      } catch (err) {
        trackSilentException(err)
      }
    },
    updateInput() {
      const input = this.$refs.input
      if (this.initialWidth < 0) this.initialWidth = input.scrollWidth
      let value = input.value.trim()
      input.style.width = "1px"
      input.style.width = (value ? input.scrollWidth : this.initialWidth) + "px"
      this.url = ROOM_PATH + (value || this.defaultName)
    },
    charAnimation() {
      setTimeout(() => {
        let input = this.$refs.input
        if (input) {
          this.currentChar++
          this.$refs.input.value = this.defaultName.substr(0, this.currentChar)
          this.updateInput()
          if (this.currentChar < this.defaultName.length) {
            this.charAnimation()
          }
        }
      }, 100)
    },
  },
  watch: {
    room() {
      this.updateInput()
    },
  },
  async mounted() {
    await this.$nextTick()

    const input = this.$refs.input
    if (input) {
      input.style.width = input.scrollWidth + "px"
      this.updateInput()

      this.observer = new ResizeObserver(this.updateInput)
      this.observer.observe(document.body)

      this.charAnimation()

      if (
        !/Android|webOS|iPhone|iPad|iPod|Opera Mini/i.test(navigator.userAgent)
      ) {
        input.focus()
      }
    }
  },

  beforeDestroy() {
    this.observer?.disconnect()
  },
}
</script>
