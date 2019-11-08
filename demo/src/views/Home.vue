<template>
    <div class="home">
        <Child :tit="title" @get="getCon" ref="child"></Child>
        <InputTxt></InputTxt>
        <List></List>
        <div ref="red">红色的box</div>
        <input type="text" v-focus v-bind:value="title" @input="ipt">
    </div>
</template>

<script>
// @ is an alias to /src
import Child from '@/components/child'
import InputTxt from '@/components/input-txt'
import List from '@/components/list'
export default {
    name: 'home',
    data(){
        return {
            title:'父组件的数组'
        }
    },
    components: {
        Child,
        InputTxt,
        List
    },
    mounted() {
        // console.log("chilren",this.$children[0].con)
        console.log(this.$refs.child.con)
        this.$refs.red.style.background = 'red';
    },
    methods:{
        getCon(con){
            console.log(con)
        },
        ipt(event){
            this.title = event.target.value;
        }
    },
    // 注册指令
    directives:{
        focus: {
            // 指令的定义
            inserted: function (el) {
                el.focus()
            }
        }
    }
}
</script>
