<template>
  <div class="container">
    activeTab {{activeTab}}
    <ul class="tabmenu">
      <li>
        <a
          href
          v-on:click.prevent="activeTab = 1"
          v-bind:class="{active: activeTab === 1 ? true : false }"
        >HOME</a>
      </li>
      <li>
        <a
          href
          v-on:click.prevent="activeTab = 2"
          v-bind:class="{active: activeTab === 2 ? true : false }"
        >FRENDS</a>
      </li>
      <li>
        <a
          href
          v-on:click.prevent="activeTab = 3"
          v-bind:class="{active: activeTab === 3 ? true : false }"
        >FHOTO</a>
      </li>
    </ul>
    <section v-show="activeTab === 1" class="contentsFlame">
      a
      <contents1></contents1>
    </section>
    <section v-show="activeTab === 2" class="contentsFlame">
      b
      <contents2></contents2>
    </section>
    <section v-show="activeTab === 3" class="contentsFlame">
      c
      <contents3></contents3>
    </section>
  </div>
</template>

<script>
import contents1 from "./contents1.vue";
import contents2 from "./contents2.vue";
import contents3 from "./contents3.vue";

export default {
  name: "tab",
  data: function() {
    return {
      activeTab: 1
    };
  },
  props: {},
  components: {
    contents1: contents1,
    contents2: contents2,
    contents3: contents3
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  margin: 0 auto;
  width: 800px;
}

.tabmenu {
  display: flex;
  margin: 35px 0 0 0;
  padding: 0;
}

.tabmenu li {
  list-style: none;
}

.tabmenu li a {
  font-size: 20px;
  /* color: #fff; */
  text-decoration: none;
  display: inline-block;
  text-align: center;
  width: 100px;
  padding: 8px 0;
  border-radius: 4px 4px 0 0;
}
.tabmenu li a.active {
  background: #333;
  /* color: #fff; */
}

/* .contentsFlame {
  display: none;
} */

.contentsFlame {
  background: #333;
  color: #fff;
  display: block;
  min-height: 150px;
  padding: 12px;
  width: 600px;
}
</style>
