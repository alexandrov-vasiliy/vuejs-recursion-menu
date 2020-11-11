<template>

    <div   class="item" :class="{haveSub: item.subMenu} ">

        <div class="menu__item" @click="OpenSubMenu" :class="{focus: item.show}">
            <span class="menu__text" v-if="item.text">{{item.text}}</span>
            <span class="menu__title" v-if="item.title">{{item.title}}</span>
        </div>
        <div class="menu__subs"  v-show="item.show" >
            <menu-item
                    @open-sub="OpenSubMenu"
                    v-for="(subMenu , subIndex) in item.subMenu"
                    :item="subMenu"
                    :key="subIndex"
            ></menu-item>
        </div>

    </div>

</template>

<script>
    export default {
        name: "MenuItem",
        props: {

            item:Object,

        },
        data(){
            return{

            }
        },
        methods:{
            OpenSubMenu(event){
                console.log(event.target.dataset.id);

                if(this.item.subMenu)
                this.item.show = !this.item.show


            },
        },
        mounted() {
            this.$set(this.item,'show',false);

        }
    }
</script>

<style scoped>
    .item{
        max-width: 250px;
    }
    .menu__item{
        text-transform: uppercase;
        padding: 10px;
        border: 1px solid #fff;
        background-color: rgba(28, 28, 28, 0.45);
        color: #fff;
        width: 250px;
        height: 40px;
        font-size: 14px;
        display: flex;
        align-items: center;
        cursor: pointer;
        margin: 10px 0 0 10px;
        font-weight: bold;
        min-width: 250px;
    }
    .haveSub{
        display: grid;
        grid-template-columns: repeat(2,290px);
        grid-template-rows: repeat(1,70px);
    }
    .menu__subs{
        display: flex;

        flex-direction: column;
    }
    .focus{
        color: #fb9b1a;
        background-color: rgba(0, 0, 0, 0.5);
    }
</style>
