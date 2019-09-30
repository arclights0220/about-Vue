<template>
    <div id="app">
        <!--        <input type="text" v-model="str">-->
        <!--        {{getReverseCom()}}-->
        <input type="text" id="texts" v-model="tel">
    </div>
</template>

<script>
    export default {
        //     data(){
        //         return  {
        //             str :  ""
        //         }
        //     },
        //     methods : {
        //         getReverseCom(){
        //             console.log("adsf")
        //             return this.str.split("").reverse().join("")
        //         }
        //     },
        //
        //     computed: {
        //         getReverse(){
        //             console.log("adsf")
        //             return this.str.split("").reverse().join("")
        //         }
        //     }
        // }

        data() {
            //내부 변수 선언
            return {
                tel : ""
            }
        },
        created(){
            //페이지가 로드되기 전에 한번 실행
        },
        mounted(){
            //페이지가 로드된 후에 한번 실행
        },
        methods : {
            //내부 함수 저장
        },
        props: {
            //속성값으로 넘겨받을 때 씀
            //Class: String
        },
        components : {
            //다른 컴포넌트를 불러옴?(.vue 파일)
        },
        computed: {
            //계산된 값을 반환하는 함수 들
        },

        watch: {
            tel(next, prev){
                let key = next.length > prev.length ? next[prev.length] : -1;
                if(!isNaN(parseInt(key)) && next.length < 14){
                    if(prev[prev.length-1] == "-" && key == -1){
                        this.tel = next.slice(0, -1)
                    }
                    else if(next.length == 3 || next.length == 8){
                        this.tel += "-";
                    }
                }
               else{
                   if(key != "-"){
                       this.tel = prev
                   }
                }
            }
        }
    }
</script>

