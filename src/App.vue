
<template>
  <div id="app">
    <div class="bg-container">
      <menu-item :item="item" v-for="(item, index) in menuData" :key="index"></menu-item>
    </div>
  </div>
</template>

<script>
  import MenuItem from "./components/MenuItem";


export default {
  name: 'App',
  components: {

    MenuItem
  },
  data(){
    return {

      subMenuShow: false,
      menuData: [
        {
          "text": "Пункт меню с действием",
          "action": "actionName"
        },
        {
          "text": "Пункт меню с подпунктами",
          "subMenu": [
            {
              "title": " Пункт меню с подпунктами ",
              "icon": "car",
              "subMenu": [
                {
                  text: 'Пункт меню без действий',
                }, {
                  text: 'Пункт меню без действий',

                },
              ],
            },
            {
              "title": "Пункт меню без действий",
            }
          ]
        },{
          "text": "Пункт меню с подпунктами",
          "subMenu": [
            {
              "title": " Пункт меню с подпунктами ",
              "icon": "car",
              "subMenu": [
                {
                  text: 'Пункт меню без действий',
                }, {
                  text: 'Пункт меню без действий',

                },
              ],
            },
            {
              "title": "Пункт меню без действий",
            }
          ]
        },
        {
          "text": "Пункт меню с подпунктами",
          "subMenu": [
            {
              "title": " Пункт меню с подпунктами ",
              "icon": "car",
              "subMenu": [
                {
                  "text": "Пункт меню с подпунктами",
                  "subMenu": [
                    {
                      "title": " Пункт меню с подпунктами ",
                      "icon": "car",
                      "subMenu": [
                        {
                          text: 'Пункт меню без действий',
                        }, {
                          text: 'Пункт меню без действий',

                        },
                      ],
                    },
                    {
                      "title": "Пункт меню без действий",
                    }
                  ]
                }, {
                  text: 'Пункт меню без действий',

                },
              ],
            },
            {
              "title": "Пункт меню без действий",
            }
          ]
        },
      ],

    }
  },
  methods:{
    OpenSubMenu(event){
        console.log(event.target.dataset.id);
        this.subMenuShow = true;
    }
  },

}
</script>
<style>
  body{
    margin: 0;
    padding: 0;
      font-family: sans-serif;
  }
</style>

<style scoped>
    .bg-container {
        background-image: url("assets/bg.png");
        background-repeat: no-repeat;
        background-size: cover;
        margin: 0;
        padding: 0;
        height: 100vh;
        overflow: auto;

    }
    .item{
        display: flex;
    }

    .menu{
        display: flex;
        flex-direction: column;
        align-items: flex-start;


        min-height: 300px;
    }

</style>
