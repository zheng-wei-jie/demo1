<template>
    <div>
            我是列表页
            <ul>
                <li v-for="item of newList" :key="item.id"> {{ item.title }} </li>
            </ul>
    </div>
</template>
<script setup>

// 在nuxt当中我们不可以打开页面之后再去ajax请求获取数据，因为这样字就跟单页应用无区别了。
//使用useFetch可以帮我们一开始的时候先获取到数据 然后再进行页面数据的渲染 确保nuxt返回的内容是获取了数据并且完成了
// 渲染的结果
const res = await useFetch('https://cnodejs.org/api/v1/topics')
console.log('res',res.data.value)
const newList = ref([]);
newList.value = res.data.value.data

</script>