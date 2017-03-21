<template>
    <div>
        <scroller class="appmain">   
            <div class="box">
                <div  v-for="(val,key) in group"  v-if="val.length!=0">
                    <div class="box-title" :id="key">
                        <text class="txt1" v-if="key=='ZZ'">#</text>
                        <text class="txt1" v-else>{{key}}</text>
                    </div>
                  <div class="box1" v-for="t,index in val" @click="clk(index)">  
                    <text class="txt2" >{{t}}</text>
                  </div>
                </div>
            </div>
        </scroller>
        <div class="box2">
            <text class="txtIndex">A</text>
            <text class="txtIndex">B</text>
            <text class="txtIndex">C</text>
            <text class="txtIndex">D</text>
            <text class="txtIndex">E</text>
            <text class="txtIndex">F</text>
            <text class="txtIndex">G</text>
            <text class="txtIndex">H</text>
            <text class="txtIndex">I</text>
            <text class="txtIndex">J</text>
            <text class="txtIndex">K</text>
            <text class="txtIndex">L</text>
            <text class="txtIndex">M</text>
            <text class="txtIndex">N</text>
            <text class="txtIndex">O</text>
            <text class="txtIndex">P</text>
            <text class="txtIndex">Q</text>
            <text class="txtIndex">R</text>
            <text class="txtIndex">S</text>
            <text class="txtIndex">T</text>
            <text class="txtIndex">U</text>
            <text class="txtIndex">V</text>
            <text class="txtIndex">W</text>
            <text class="txtIndex">X</text>
            <text class="txtIndex">Y</text>
            <text class="txtIndex">Z</text>
            <text class="txtIndex">#</text>
        </div>
    </div>
</template>
<script>
    // import pinyin from 'pinyin'

    export default {
        props: ['department'],
        data() {
            return {
                depList: [],
                group: {
                    A: [],
                    B: [],
                    C: [],
                    D: [],
                    E: [],
                    F: [],
                    G: [],
                    H: [],
                    I: [],
                    J: [],
                    K: [],
                    L: [],
                    M: [],
                    N: [],
                    O: [],
                    P: [],
                    Q: [],
                    R: [],
                    S: [],
                    T: [],
                    U: [],
                    V: [],
                    W: [],
                    X: [],
                    Y: [],
                    Z: [],
                    ZZ: [],
                }
            }
        },
        methods: {
            clk(index) {
                this.$emit('clk', index)
            }
        },
        created() {
            this.depList = this.department;
            let dl = this.depList;
            dl = this.department
            for (let i = 0; i < dl.length; i++) {
                let cell = pinyin(dl[i]).join();
                let c = cell.substring(0, 1);
                if (c == 'a') {
                    this.group.A.push(dl[i])
                } else if (c == 'b') {
                    this.group.B.push(dl[i])
                } else if (c == 'c') {
                    this.group.C.push(dl[i])
                } else if (c == 'd') {
                    this.group.D.push(dl[i])
                } else if (c == 'e') {
                    this.group.E.push(dl[i])
                } else if (c == 'f') {
                    this.group.F.push(dl[i])
                } else if (c == 'g') {
                    this.group.G.push(dl[i])
                } else if (c == 'h') {
                    this.group.H.push(dl[i])
                } else if (c == 'i') {
                    this.group.I.push(dl[i])
                } else if (c == 'j') {
                    this.group.J.push(dl[i])
                } else if (c == 'K') {
                    this.group.K.push(dl[i])
                } else if (c == 'l') {
                    this.group.L.push(dl[i])
                } else if (c == 'm') {
                    this.group.M.push(dl[i])
                } else if (c == 'n') {
                    this.group.N.push(dl[i])
                } else if (c == 'o') {
                    this.group.O.push(dl[i])
                } else if (c == 'p') {
                    this.group.P.push(dl[i])
                } else if (c == 'q') {
                    this.group.Q.push(dl[i])
                } else if (c == 'r') {
                    this.group.R.push(dl[i])
                } else if (c == 's') {
                    this.group.S.push(dl[i])
                } else if (c == 't') {
                    this.group.T.push(dl[i])
                } else if (c == 'u') {
                    this.group.U.push(dl[i])
                } else if (c == 'v') {
                    this.group.V.push(dl[i])
                } else if (c == 'w') {
                    this.group.W.push(dl[i])
                } else if (c == 'x') {
                    this.group.X.push(dl[i])
                } else if (c == 'y') {
                    this.group.Y.push(dl[i])
                } else if (c == 'z') {
                    this.group.Z.push(dl[i])
                } else {
                    this.group.ZZ.push(dl[i])
                }
            }
            console.log(this.group)
        }
    }
</script>

<style scoped>
    .box-title {
        width: 750px;
        height: 34px;
        background-color: #f5f5f4;
    }
    
    .box2 {
        position: absolute;
        top: 140px;
        right: 10px;
        flex-direction: column;
    }
    
    .txtIndex {
        flex: 1;
        font-size: 26px;
        color: #008dfc;
        margin-top: 4px;
        margin-bottom: 3px;
    }
    
    .txt1 {
        font-size: 28px;
        margin-left: 30px;
    }
    
    .txt2 {
        font-size: 28px;
        margin-left: 30px;
    }
    
    .appmain {
        position: absolute;
        background-color: #f5f5f4;
        top: 100px;
        bottom: 110px;
        width: 750px;
        left: 0px;
    }
    
    .box {
        width: 750;
        flex-direction: column;
        margin-top: 10px;
    }
    
    .box1 {
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        background-color: white;
        margin-top: 10px;
        width: 750px;
        height: 80px;
        border-bottom-width: 1px;
        border-bottom-style: solid;
        border-color: #d9d9d9;
    }
</style>