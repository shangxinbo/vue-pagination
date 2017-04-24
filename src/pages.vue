<style>
    .page {
        width: 100%;
        height: 28px;
        text-align: center;
        padding: 35px 0 10px;
        font-size: 0
    }
    
    .page a {
        display: inline-block;
        text-decoration: none;
        vertical-align: top;
        min-width: 28px;
        height: 28px;
        background-color: #fff;
        border: 1px solid #d8d9de;
        border-radius: 4px;
        color: #4c4c4c;
        font-size: 14px;
        line-height: 29px;
        overflow: hidden;
        margin: 0 4px
    }
    
    .page a:hover {
        background-color: #FFF
    }
    
    .page a.next,
    .page a.prev {
        width: 66px
    }
    
    .page a.active {
        cursor: default;
        background-color: #15c1ff;
        border-color: #e9e9e9;
        color:white
    }
    
    .page a.disabled {
        display: none
    }
    
    .page span {
        display: inline-block;
        vertical-align: top;
        width: 12px;
        height: 28px;
        margin: 0 3px;
        font-size: 14px;
        line-height: 22px
    }
</style>
<template>
    <div class="page" v-show="total>1">
        <a class="prev" :class="{disabled:current==1}" @click="goPage(current-1)" href="javascript:void(0);">上一页</a>
        <a href="javascript:void(0);" :class="{active:current==1}" @click="goPage(1)">1</a>
        <template v-if="total>7">
            <template v-if="current<=4">
                <a href="javascript:void(0);" :class="{active:current==2}" @click="goPage(2)">2</a>
                <a href="javascript:void(0);" :class="{active:current==3}" @click="goPage(3)">3</a>
                <a href="javascript:void(0);" :class="{active:current==4}" @click="goPage(4)">4</a>
                <a href="javascript:void(0);" :class="{active:current==5}" @click="goPage(5)">5</a>
                <span>...</span>
                <a href="javascript:void(0);" :class="{active:current==total}" @click="goPage(total)">{{total}}</a>
            </template>
            <template v-else>
                <template v-if="current<=(total-4)">
                    <span>…</span>
                    <a href="javascript:void(0);" @click="goPage(current-1)">{{current-1}}</a>
                    <a href="javascript:void(0);" class="active" @click="goPage(current)">{{current}}</a>
                    <a href="javascript:void(0);" @click="goPage(parseInt(current)+1)">{{parseInt(current)+1}}</a>
                    <a href="javascript:void(0);" @click="goPage(parseInt(current)+2)">{{parseInt(current)+2}}</a>
                    <span>…</span>
                    <a href="javascript:void(0);" @click="goPage(total)">{{total}}</a>
                </template>
                <template v-else>
                    <span>…</span>
                    <a href="javascript:void(0);" :class="{active:current==total-4}" @click="goPage(total-4)">{{total-4}}</a>
                    <a href="javascript:void(0);" :class="{active:current==total-3}" @click="goPage(total-3)">{{total-3}}</a>
                    <a href="javascript:void(0);" :class="{active:current==total-2}" @click="goPage(total-2)">{{total-2}}</a>
                    <a href="javascript:void(0);" :class="{active:current==total-1}" @click="goPage(total-1)">{{total-1}}</a>
                    <a href="javascript:void(0);" :class="{active:current==total}" @click="goPage(total)">{{total}}</a>
                </template>
            </template>
        </template>
        <template v-else>
            <a href="javascript:void(0);" @click="goPage(2)" :class="{active:current==2}">2</a>
            <a v-if="total>2" href="javascript:void(0);" :class="{active:current==3}" @click="goPage(3)">3</a>
            <a v-if="total>3" href="javascript:void(0);" :class="{active:current==4}" @click="goPage(4)">4</a>
            <a v-if="total>4" href="javascript:void(0);" :class="{active:current==5}" @click="goPage(5)">5</a>
            <a v-if="total>5" href="javascript:void(0);" :class="{active:current==6}" @click="goPage(6)">6</a>
            <a v-if="total>6" href="javascript:void(0);" :class="{active:current==7}" @click="goPage(7)">7</a>
        </template>
        <a class="next" href="javascript:void(0);" v-show="current<total" @click="goPage(parseInt(current)+1)">下一页</a>
    </div>
</template>
<script>
    export default {
        props: ['total', 'current'],
        methods: {
            goPage: function (page) {
                this.$emit('jump', page)
            }
        }
    }

</script>