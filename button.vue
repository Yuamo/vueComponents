<template>
    <div class="button" :style="{width:btn.width+'px',height:btn.height+'px',backgroundColor:backg}" @click="enter">
        <text class="txtbtn" :style="{color: btn.color,fontSize:btn.fontsize+'px'}">{{btn.value}}</text>
    </div>
</template>
<script>
    export default {
        props: ['btn'],
        data() {
            return {
                backg: ''
            }
        },
        methods: {
            enter(event) {
                this.$emit('enter');

                // 当按钮按下修改按钮的颜色
                let col = this.backg;
                let r1 = parseInt(col.substring(1, 3), 16) - 50;
                let r = r1 >= 0 ? r1 : parseInt(col.substring(1, 3), 16);
                let g1 = parseInt(col.substring(3, 5), 16) - 50;
                let g = g1 >= 0 ? g1 : parseInt(col.substring(3, 5), 16);
                let b1 = parseInt(col.substring(5, 7), 16) - 50;
                let b = b1 >= 0 ? b1 : parseInt(col.substring(5, 7), 16);
                this.backg = 'rgb(' + r + ',' + g + ',' + b + ')';
            }
        },
        created() {
            this.backg = this.btn.background;
        }
    }
</script>

<style scoped>
    .button {
        border-radius: 10px;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }
    
    .txtbtn {
        text-align: center;
    }
</style>