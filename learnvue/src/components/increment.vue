<template>
    <div>
        <h2>加减法计算器</h2>
        <div>
            <input type="button" value="-" @click="minHandle">
                <span>{{num}}</span>
            <input type="button" value="+" @click="addHandle">
        </div>
        <div>
            <p>姓名：{{name}}</p>
            <p>年龄：{{age}}</p>
            <p>getters得到的num2: {{num2}}</p>
        </div>
    </div>
</template>

<script>
    import { mapState } from 'vuex'
    export default{

        // 赋值方法三 最方便最长用的方法
        computed:{
            num(){
                return this.$store.state.num
            },
            name(){
                return this.$store.state.name
            },
            age(){
                return this.$store.state.age
            },
            num2(){
                return this.$store.getters.count;
            }
        },
        methods:{
            minHandle(){
                // this.num -= 5;
                this.$store.commit('MinIncrement');
            },
            addHandle(){
                // console.log(this.$store.state.num);
                // this.num += 5;
                // 通过这里提交一个mutations,commit
                this.$store.commit('AddIncrement');
            }
        }
    }
</script>
