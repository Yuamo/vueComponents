<template>
    <div>
        <div class="box1">
            <image class="box1img1" :src="imgsrc1" @click="rightm"></image>
            <text class="box1txt">选择预约时间</text>  
            <image class="box1img2" :src="imgsrc2" @click="leftm"></image>
        </div>
        <div class="box">
            <div class="box2"   v-for="d,index in dateList" >
                <div  class="title" >
                    <text  class="box2txt" >{{d}}</text>
                </div>
            </div>
        </div>
        <div class="box">
            <div class="box2"   v-for="d,index in dateList" @click="selAmTime(d,index)">
                <div  class="title" >
                    <text  class="box2txt" >上午</text>
                </div>
            </div>
        </div>
        <div class="box">
            <div class="box2"   v-for="d,index in dateList" @click="selPmTime(d,index)">
                <div  class="title" >
                    <text  class="box2txt" >下午</text>
                </div>
            </div>
        </div>
        <!--时间选择-->
        <div class="sel-time" v-if="Am">
            <div class="time-title">
                <text class="txt" value="">2017.3.21 上午</text>
            </div>
            <div class="times"  v-for="(time,index) in timeAmList">
                <text class="txt1" :value="time"></text>
            </div>
        </div>
        <div class="sel-time" v-if="Pm">
            <div class="time-title">
                <text class="txt" value="">2017.3.21 上午</text>
            </div>
            <div class="times"  v-for="(time,index) in timePmList">
                <text class="txt1" :value="time"></text>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                Am: false,
                Pm: false,
                imgsrc1: './src/assets/images/index/hospitalDetail/bespeak/gray@2x.png',
                imgsrc2: './src/assets/images/index/hospitalDetail/bespeak/blue@2x.png',
                dateList: [],
                dateAllList: [],
                timeAmList: [
                    '09:00',
                    '09:15',
                    '09:30',
                    '09:45',
                    '10:00',
                    '10:15',
                    '10:30',
                    '10:45',
                    '11:00',
                    '11:15',
                    '11:30',
                    '11:45',
                    '12:00',
                ],
                timePmList: [
                    '09:00',
                    '09:15',
                    '09:30',
                    '09:45',
                    '10:00',
                    '10:15',
                    '10:30',
                    '10:45',
                    '11:00',
                    '11:15',
                    '11:30',
                    '11:45',
                    '12:00',
                ]
            }
        },
        methods: {
            selAmTime(d, index) {
                this.Am = true;
            },
            selPmTime(d, index) {
                this.Pm = true;
            },

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
    .time-title {
        flex-direction: row;
        align-items: center;
        justify-content: center;
        height: 90px;
        border-color: black;
        border-width: 1px;
        border-style: solid;
    }
    
    .sel-time {
        position: absolute;
        bottom: 0px;
        width: 750px;
        flex-direction: column;
        background-color: rgba(200, 200, 200, 0.5);
        z-index: 99;
    }
    
    .times {
        width: 750px;
        height: 80px;
    }
    
    .txt1 {
        font-size: 30px;
        margin-left: 30px;
        padding-top: 10px;
        padding-bottom: 10px;
    }
    
    .box2txt {
        font-size: 24px;
        color: #008dfc;
        text-align: center;
    }
    
    .box2 {
        flex: 1;
        justify-content: center;
        align-items: center;
        width: 108px;
        height: 108px;
        border-right-width: 1px;
        border-right-color: #d9d9d9;
        border-right-style: solid;
        border-bottom-width: 1px;
        border-bottom-color: #d9d9d9;
        border-bottom-style: solid;
    }
    
    .box {
        width: 750px;
        height: 108px;
        flex-direction: row;
        align-items: center;
    }
    
    .box1img1 {
        width: 38px;
        height: 38px;
        margin-left: 15px;
    }
    
    .box1img2 {
        width: 38px;
        height: 38px;
        margin-right: 15px;
    }
    
    .box1txt {
        font-size: 30px;
        color: #008dfc;
    }
    
    .box1 {
        width: 750px;
        height: 90px;
        background-color: #f3f3f3;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
</style>