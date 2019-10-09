<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
    <!-- 基础练习 -->
    <div id="vue_det">
      <h1>site: {{site}}</h1>
      <h1>url: {{url}}</h1>
      <h1>{{details()}}</h1>
    </div>
    <!-- 渲染HTML结构 -->
      <div v-html="mssageg"></div>
      <!-- 点击修改颜色 -->
      <label for="r1">修改颜色</label><input type="checkbox" v-model="use" id="r1">
      <br>
      <div v-bind:class="{'class1': use}">
        v-bind:class指令

      </div>

      <hr>
      <!-- 点击反转字符串 -->
      <p>{{yturn}}</p>
      <button v-on:click="reversMessage">反转字符串</button>
      <hr>
      <!-- 过滤器 -->
        {{kjs | capitalize}}
        <hr>
        <!-- v-if 显示隐藏 -->
      <p v-if="seen">现在你看到我了</p>
      <div v-if="ok">
        <h1>打字辛苦</h1>
        <h1>离开教室里</h1>
        <h1>.孟子见梁襄王</h1>
      </div>
      <button @click="dianj">点击显示隐藏</button>
      <hr>
      <!-- v-if v-if-else v-else -->

      <div v-if="Math.random() > 0.5">
        sorry
      </div>
      <div v-else>
        not sorry
      </div>

      <div v-if="type === 'A'">
        A
      </div>
      <div v-else-if="type === 'B'">
        B
      </div>
      <div v-else-if="type === 'C'">
        C
      </div>
      <div v-else>
        not A/B/C
      </div>
      <hr>
      <!-- v-show -->

      <h1 v-show="ok">Hello</h1>
      <button @click="isShow">点击显示和隐藏</button>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function() {
    return {
      site: '菜鸟教程',
      url: 'www.runoob.com',
      alexa: '10000',
      mssageg: '<h1>home live statry laljh</h1>',
      use: false,
      yturn: 'dljlsjldjsjsljhuwwi',
      kjs: 'ljjialjwiej',
      seen: true,
      ok: true,
      type: 'C'
    };
  },
  filters: {
    capitalize: function(value) {
      if (!value) return ''
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1);
    }
  },
  methods: {
    details: function() {
      return this.site + ' - 学到不仅是技术,更是梦想!';
    },
    reversMessage: function() {
      this.yturn = this.yturn.split('').reverse().join('');
    },
    dianj: function() {
      this.seen = !this.seen;
    },

    isShow() {
      this.ok = !this.ok;
    }
  }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>

.class1 {
  background: #444;
  color: #42b983;
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
