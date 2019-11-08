<template>
    <div>
        child 

        tit === {{tit}}

        <button @click="$emit('get',con)">子向父传递数据</button>
    </div>
</template>

<script>
export default {
    props:['tit'],
    data(){
        return {
            con:'子级的数据'
        }
    },
    mounted() {
        console.log(this.$parent.title)
    },
}
</script>
