

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  render(h) {
    return <div class="mainContainer">{this.rows(h)}</div>;
  },
  methods: {
    blocks(h, ri) {
      return new Array(ri * 3).fill(1).map((n, i) => <div class="item"></div>);
    },
    rows(h) {
      return new Array(5)
        .fill(1)
        .map((c, i) => <div class={`container`}>{this.blocks(h, i + 1)}</div>);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.mainContainer {
  display: flex;
  flex-direction: column;
}

.container {
  display: flex;
  flex-wrap: wrap; /* */
  align-items: center;
  justify-content: space-around; /* */
  height: 150px;
  background: gray;
  border: 1px solid white;
}

.item {
  display: flex;
  height: 100px;
  border: 1px solid black;
  flex-grow: 1;
  flex-shrink: 0.5;
  max-width: 100px;
  flex-basis: 50px;
}

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
</style>
