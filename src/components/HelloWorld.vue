<template>
  <div class="hello">
    <h1>
      Welcome to
      <span class="typing">
        {{ title_yaeverse.text }}
      </span>
    </h1>
    <p>The open-source hyper-metaverse based on instant messaging. 💬</p>
    <h3>Essential Links</h3>
    <ul>
      <li>
        <a href="https://github.com/yaeverse" target="_blank" rel="noopener"
          >GitHub Organization</a
        >
      </li>
      <li>
        <a href="https://github.com/yaeverse/yae" target="_blank" rel="noopener"
          >Repository of Yae</a
        >
      </li>
      <li>
        <a
          href="https://github.com/yaeverse/yaeverse"
          target="_blank"
          rel="noopener"
          >Repository of Yaeverse</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => ({
    title_yaeverse: {
      text: "",
      message: "Yaeverse🦊",
      typeSpeed: 100,
      backSpeed: 60,
      loop: true,
    },
  }),
  methods: {
    typing(target, isBack) {
      const { text, message, typeSpeed, backSpeed, loop } = target;
      if (isBack && !loop) {
        return;
      } else {
        target.text = message.substring(0, text.length + (!isBack ? 1 : -1));
      }
      isBack =
        text.length === message.length
          ? true
          : text.length === 0
          ? false
          : isBack;
      const speed =
        text.length + 1 === message.length
          ? 3_600
          : isBack
          ? backSpeed
          : typeSpeed;
      setTimeout(() => this.typing(target, isBack), speed);
    },
  },
  mounted() {
    this.typing(this.title_yaeverse);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #b42983;
}

.typing {
  color: #b42983;
  font-family: "Courier New", Courier, monospace;
  font-size: 1.5em;
  font-weight: bold;
  white-space: nowrap;
  overflow: hidden;
  border-right: 0.15em solid orange;
  margin: 0 auto;
  animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
}

@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}

@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: orange;
  }
}
</style>
