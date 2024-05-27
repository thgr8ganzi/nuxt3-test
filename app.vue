<template>
  <h1>{{ msg }}</h1>
  <ChildComponent v-model="msg" />
</template>

<script setup>
import { ref } from 'vue';
import ChildComponent from './components/ChildComponent.vue';

const msg = ref('Hello World!');
</script>

<!--<template>-->
<!--  <h1>{{ msg }}</h1>-->
<!--  <Child v-model="msg" />-->
<!--</template>-->

<!--<script setup>-->
<!--import Child from './components/ChildComponent.vue'-->

<!--const msg = ref('Hello World!')-->
<!--</script>-->
<!--<template>-->
<!--  <div>-->
<!--    <input type="text" v-model=inputValue1>-->
<!--    <input type="text" :value="inputValue2" @input="inputValue2 = $event.target.value">-->
<!--  </div>-->
<!--  <div>{{inputValue1}}</div>-->
<!--  <div>{{inputValue2}}</div>-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      inputValue1: '',-->
<!--      inputValue2: '',-->
<!--    }-->
<!--  },-->
<!--  computed: {-->

<!--  },-->
<!--  methods: {-->

<!--  }-->
<!--}-->
<!--</script>-->
<!--<template>-->
<!--  <div>-->
<!--    부모컴포넌트-->
<!--    <ChildComponent @send-event="parentEvent"/>-->
<!--  </div>-->
<!--</template>-->
<!--<script setup lang="ts">-->

<!--const parentEvent = (event:string) => {-->
<!--  console.log(event)-->
<!--}-->
<!--</script>-->
<!--<template>-->
<!--  <div>-->
<!--    <ChildComponent v-bind:sendProps1="title" v-bind:sendProps2="createAt" :send-props3="obj"/>-->
<!--  </div>-->
<!--</template>-->
<!--<script setup lang="ts">-->
<!--import { ref } from "vue";-->
<!--import ChildComponent from "./components/ChildComponent.vue";-->
<!--interface Obj {-->
<!--  id: number;-->
<!--  name: string;-->
<!--}-->
<!--const title = ref<string>('부모 컴포넌트에서 선언된 데이터');-->
<!--const createAt = ref<number>(2024);-->
<!--const obj = reactive<Obj>({-->
<!--  id: 1,-->
<!--  name: '홍길동',-->
<!--})-->
<!--// export default {-->
<!--//   components: {-->
<!--//     ChildComponent-->
<!--//   },-->
<!--//   data() {-->
<!--//     return {-->
<!--//       title: "부모 컴포넌트에서 선언된 데이터",-->
<!--//       createAt: 2024,-->
<!--//       obj: {-->
<!--//         name: "홍길동",-->
<!--//         age: 20-->
<!--//       }-->
<!--//     };-->
<!--//   },-->
<!--// }-->
<!--</script>-->
<!--<style>-->
<!--</style>-->
<!--<template>-->
<!--  <button @click="changeMessage">-->
<!--    {{message}}-->
<!--  </button>-->
<!--  {{watchMessage}}-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      message: 'Hello Vue.js!',-->
<!--      watchMessage: '',-->
<!--    }-->
<!--  },-->
<!--  watch: {-->
<!--    message(newValue, oldValue) {-->
<!--      this.watchMessage = 'watcher: ' + newValue + ' / ' + oldValue-->
<!--    }-->
<!--  },-->
<!--  methods: {-->
<!--    changeMessage() {-->
<!--      console.log('changeMessage!!')-->
<!--      this.message = 'Hello Vue.js 3! asdasdasd'-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->
<!--<style>-->

<!--</style>-->
<!--<template>-->
<!--  <div>-->
<!--    <h1>{{text}}</h1>-->
<!--    <h1>change text : {{changeText()}}</h1>-->
<!--    <h1>change text : {{changeText()}}</h1>-->
<!--    <h1>change text : {{changeText()}}</h1>-->
<!--    <h2>computed text : {{computedText}}</h2>-->
<!--    <h2>computed text : {{computedText}}</h2>-->
<!--    <h2>computed text : {{computedText}}</h2>-->
<!--  </div>-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      text: 'Computed'-->
<!--    }-->
<!--  },-->
<!--  computed: {-->
<!--    computedText() {-->
<!--      console.log('computed', this.text)-->
<!--      return this.text.split('').reverse().join('');-->
<!--    }-->
<!--  },-->
<!--  methods: {-->
<!--    changeText() {-->
<!--      this.text = 'Changed';-->
<!--      console.log("methods", this.text);-->
<!--      return this.text.split('').reverse().join('');-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->
<!--<style>-->

<!--</style>-->
<!--<template>-->
<!--  <div>-->
<!--    <button v-on:click="count++">인라인 핸들러++</button>-->
<!--    <button @click="count&#45;&#45;">인라인 핸들러&#45;&#45;</button>-->
<!--    <h1>{{count}}</h1>-->
<!--    <button v-on:click="changeName">메소드 핸들러++</button>-->
<!--    <h1>{{name}}</h1>-->
<!--  </div>-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--    data() {-->
<!--      return {-->
<!--        count: 0,-->
<!--        name: 'vue.js 3'-->
<!--      }-->
<!--    },-->
<!--    methods: {-->
<!--      changeName() {-->
<!--        this.name = 'vue.js ' + Math.round(Math.random() * 3);-->
<!--      }-->
<!--    }-->
<!--}-->
<!--</script>-->
<!--<style>-->

<!--</style>-->
<!--<template>-->
<!--  <div>-->
<!--    <li v-for="(item, index) in sampleData" :key="item">{{index}} : {{item}}</li>-->
<!--    <li v-for="(item, index) in otherArr" :key="item">{{index}} : {{item.id}} = {{item.name}}</li>-->
<!--  </div>-->
<!--</template>-->
<!--<script>-->
<!--export default{-->
<!--  data() {-->
<!--    return {-->
<!--      sampleData: ['a', 'b', 'c', 'd', 'e'],-->
<!--      otherArr: [-->
<!--        {id: 1, name: 'a'},-->
<!--        {id: 2, name: 'b'},-->
<!--        {id: 3, name: 'c'},-->
<!--        {id: 4, name: 'd'},-->
<!--        {id: 5, name: 'e'},-->
<!--      ]-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->
<!--<template>-->
<!--  <div :class="red" v-if="isVisible"></div>-->
<!--  <div :class="blue" v-if="!isVisible"></div>-->
<!--  <div :class="black" v-else></div>-->
<!--  <div :class="red" v-if="count > 1"></div>-->
<!--  <div :class="black" v-if="count === 1"></div>-->
<!--  <div :class="blue" v-else></div>-->
<!--  <button @click="count++">증가</button>-->
<!--  <button @click="count&#45;&#45;">감소</button>-->
<!--  <div :class="red" v-show="isVisible"></div>-->
<!--  <div :class="blue" v-show="!isVisible"></div>-->
<!--  <div :class="black" v-if="isVisible"></div>-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      red: 'red',-->
<!--      blue: 'blue',-->
<!--      black: 'black',-->
<!--      isVisible: false,-->
<!--      count: 0,-->
<!--    }-->
<!--  },-->
<!--}-->
<!--</script>-->
<!--<style lang="scss">-->
<!--.red {-->
<!--  width: 100px;-->
<!--  height: 100px;-->
<!--  background-color: red;-->
<!--}-->
<!--.blue {-->
<!--  width: 100px;-->
<!--  height: 100px;-->
<!--  background-color: blue;-->
<!--}-->
<!--.black {-->
<!--  width: 100px;-->
<!--  height: 100px;-->
<!--  background-color: black;-->
<!--}-->
<!--</style>-->
<!--<template>-->
<!--  <div>{{rowHtml}}</div>-->
<!--  <div>{{rowHtml2}}</div>-->
<!--  <h1 v-html="rowHtml2"></h1>-->

<!--  <h2 v-bind:class="{active: isActive}">h2</h2>-->
<!--  <h2 :class="{active: isActive}">h2</h2>-->
<!--  <button @click="change">버튼</button>-->

<!--  <h3 style="color: aqua;font-size: large">스타일 바인딩</h3>-->
<!--  <h3 :style="{color: fontColor, fontSize: fontSize}">스타일 바인딩</h3>-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      rowHtml: "텍스트문구",-->
<!--      rowHtml2: "<span style='color: red'>HTML 문구</span>",-->
<!--      isActive: true,-->
<!--      fontColor: '#888888',-->
<!--      fontSize: '48px'-->
<!--    }-->
<!--  },-->
<!--  methods: {-->
<!--    change() {-->
<!--      this.isActive = !this.isActive;-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->
<!--<style lang="scss" scoped>-->
<!--h2.active {-->
<!--  color: green;-->
<!--}-->
<!--</style>-->
<!--<template>-->
<!--  <div>-->
<!--    {{ count }}-->
<!--  </div>-->
<!--  <h1>라이프사이클</h1>-->
<!--</template>-->
<!--<script>-->
<!--export default {-->
<!--  data() {-->
<!--    return {-->
<!--      count: 0,-->
<!--    }-->
<!--  },-->
<!--  beforeCreate() {-->
<!--    console.log('beforeCreate', this.count)-->
<!--  },-->
<!--  created() {-->
<!--    console.log('created', this.count)-->
<!--    this.test();-->
<!--  },-->
<!--  beforeMount() {-->
<!--    console.log('beforeMount', document.querySelector('h1'))-->
<!--  },-->
<!--  mounted() {-->
<!--    console.log('mounted', document.querySelector('h1'))-->
<!--  },-->
<!--  methods: {-->
<!--    test() {-->
<!--      console.log('test', this.count)-->
<!--    }-->
<!--  }-->
<!--}-->
<!--</script>-->
<!--<style lang="scss" scoped>-->

<!--</style>-->