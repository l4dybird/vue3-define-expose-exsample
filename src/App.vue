<script setup lang="ts">
import { ref } from 'vue';
import Child from './components/Child.vue';

// 子コンポーネント側のコンポーネント情報を受け取る ref を宣言しています。
const childRef = ref();

// 子コンポーネント側に渡す props を宣言しています。
const childValue = "Hello, Zenn";

// 子コンポーネント側のメソッドを発火させるメソッドを実装しています。
const onChildMethodClick = () => {
    childRef.value.childMethod();
};
</script>

<template>
    <div>
        <!-- Child コンポーネントに ref の childRef を付与します -->
        <Child ref="childRef" :value="childValue" />
        <button @click="onChildMethodClick">子コンポーネント内のメソッドを呼び出す</button>
    </div>
</template>