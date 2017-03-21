<template>
     <div class="dateWeek">
        <div class="box1">
            <image class="img1" @click="rightm"  :src="imgsrc1"></image>
        </div>
        <div class="box2"   v-for="d,index in dateList" @click="slced(index,d)" >
            <div  class="title" :style="{backgroundColor:col[index].bcol }">
                <text  class="txt" :style="{color: col[index].tcol}" >{{d}}</text>
            </div>
        </div>
        <div class="box3">
            <image class="img2" @click="leftm"  :src="imgsrc2"></image>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                imgsrc1: './src/assets/images/index/hospitalDetail/bespeak/gray@2x.png',
                imgsrc2: './src/assets/images/index/hospitalDetail/bespeak/blue@2x.png',
                col: [{
                    bcol: '#008dfc',
                    tcol: '#ffffff',
                }, {
                    bcol: '#ffffff',
                    tcol: '#008dfc'
                }, {
                    bcol: '#ffffff',
                    tcol: '#008dfc'
                }, {
                    bcol: '#ffffff',
                    tcol: '#008dfc'
                }, {
                    bcol: '#ffffff',
                    tcol: '#008dfc'
                }, {
                    bcol: '#ffffff',
                    tcol: '#008dfc'
                }],
                dateList: [],
                dateAllList: []
            }
        },
        methods: {
            rightm() {
                this.imgsrc1 = './src/assets/images/index/hospitalDetail/bespeak/gray@2x.png'
                this.imgsrc2 = './src/assets/images/index/hospitalDetail/bespeak/blue@2x.png'
                this.dateList = this.dateAllList.slice(0, 6)
                this.$emit('rightm')
            },
            leftm() {
                this.imgsrc1 = './src/assets/images/index/hospitalDetail/bespeak/leftblue@2x.png'
                this.imgsrc2 = './src/assets/images/index/hospitalDetail/bespeak/grayright@2x.png'
                this.dateList = this.dateAllList.slice(6)
                this.$emit('leftm')
            },
            slced(index, d) {
                // debugger;
                var arr_color = new Array(
                    [{
                        bcol: '#008dfc',
                        tcol: '#ffffff',
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }], [{
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#008dfc',
                        tcol: '#ffffff',
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }], [{
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#008dfc',
                        tcol: '#ffffff',
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }], [{
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#008dfc',
                        tcol: '#ffffff',
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }], [{
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#008dfc',
                        tcol: '#ffffff',
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }], [{
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#ffffff',
                        tcol: '#008dfc'
                    }, {
                        bcol: '#008dfc',
                        tcol: '#ffffff',
                    }],
                )
                this.col = arr_color[index]
                this.$emit('slced', index, d)
            }
        },
        created() {
            let dateString = new Array();
            for (let i = 0; i < 12; i++) {
                let date = new Date();
                date.setTime(date.getTime() + 24 * 60 * 60 * 1000 * i)
                var arr_week = new Array("周  日", "周  一", "周  二", "周  三", "周  四", "周  五", "周  六");
                let week = arr_week[date.getDay()];
                dateString.push(week + '\n' + (date.getMonth() + 1) + '/' + date.getDate());
            }
            // console.log(dateString)
            this.dateAllList = dateString;
            this.dateList = dateString.slice(0, 6);
        }
    }
</script>
<style scoped>
    .txt {
        font-size: 22px;
        text-align: center;
    }
    
    .img1 {
        width: 38px;
        height: 38px;
    }
    
    .img2 {
        width: 38px;
        height: 38px;
    }
    
    .box1 {
        width: 80px;
        justify-content: center;
        align-items: center;
    }
    
    .box2 {
        flex: 1;
        justify-content: center;
        align-items: center;
    }
    
    .box3 {
        width: 80px;
        justify-content: center;
        align-items: center;
    }
    
    .dateWeek {
        width: 750px;
        flex-direction: row;
        align-items: center;
        justify-content: center;
    }
    
    .title {
        flex: 1;
        width: 80px;
        height: 80px;
        align-items: center;
        justify-content: center;
        border-radius: 10px;
        border-color: #008dfc;
        border-width: 1px;
        border-style: solid;
    }
</style>