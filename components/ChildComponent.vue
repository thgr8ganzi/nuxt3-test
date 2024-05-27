<template>
  <span>My input</span> <input :value="modelValue" @input="updateValue">
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps({
  modelValue: String
});

const emits = defineEmits(['update:modelValue']);

// 입력 값이 변경될 때마다 부모 컴포넌트에 업데이트를 알림
function updateValue(event) {
  emits('update:modelValue', event.target.value);
}
</script>

<!--<template>-->
<!--  <span>My input</span> <input v-model="model">-->
<!--</template>-->

<!--<script setup>-->
<!--const model = defineModel()-->
<!--</script>-->
<!--<template>-->
<!--  <button @click="sendEvent">자식컴포넌트 버튼</button>-->
<!--</template>-->
<!--<script setup lang="ts">-->
<!--import { ref } from "vue";-->

<!--const data = ref<string>('자식컴포넌트에서 선언된 데이터')-->
<!--const emit = defineEmits(["send-event"])-->
<!--const sendEvent = () => {-->
<!--  emit("send-event", data.value)-->
<!--}-->
<!--</script>-->
<!--<template>-->
<!--  <div>-->
<!--    <div>{{sendProps1}}</div>-->
<!--    <div>{{sendProps2}}</div>-->
<!--    <div>{{sendProps3.id}}</div>-->
<!--    <div>{{sendProps3.name}}</div>-->
<!--  </div>-->
<!--</template>-->
<!--<script setup lang="ts">-->
<!--interface Obj {-->
<!--  id: number;-->
<!--  name: string;-->
<!--}-->
<!--interface Props {-->
<!--  sendProps1: string;-->
<!--  sendProps2: number;-->
<!--  sendProps3: Obj;-->
<!--}-->
<!--const props = defineProps<Props>()-->
<!--const { sendProps1, sendProps2, sendProps3 } = toRefs(props)-->
<!--// export default {-->
<!--//   props: {-->
<!--//     sendProps1: String,-->
<!--//     sendProps2: Number,-->
<!--//     sendProps3: Object-->
<!--//   },-->
<!--//   data() {-->
<!--//     return {-->
<!--//-->
<!--//     }-->
<!--//   },-->
<!--//   computed: {-->
<!--//-->
<!--//   },-->
<!--//   methods: {-->
<!--//-->
<!--//   }-->
<!--// }-->
<!--</script>-->
<!--<style>-->

<!--</style>-->