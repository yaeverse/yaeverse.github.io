<template>
  <div class="hello">
    <h1>Welcome to <span class="typing">Yaeverse🦊</span></h1>
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
  props: {
    msg: String,
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
  color: #42b983;
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
</style>
