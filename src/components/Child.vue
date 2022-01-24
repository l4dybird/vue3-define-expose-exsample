<script setup lang="ts">
// 子コンポーネントで受け取る Props の型を宣言しています。
type Props = {
    value: string;
};

// 子コンポーネントで受け取る Props を宣言しています。
const { value } = defineProps<Props>();

// defineExpose に宣言したい関数を実装しています。
const childMethod = (): void => {
    console.log(`子コンポーネントの value に ${value} が Props で渡されいます。`);
};

// defineExpose を使用してコンポーネント内に定義されたメソッドを親コンポーネントから参照できる様にしています。
defineExpose({
  childMethod,
});
</script>

<template>
    <div>
        {{ value }}
    </div>
</template>