<script >
import './HomeView.scss'
import MenuItemView from '../../components/MenuItem/MenuItemView.vue'

const users = [
    {name : 'minh',
    age: 20},
    {name : 'long',
    age: 22},
    {name : 'nam',
    age: 21}
]

const isShow = false;
const inputValue = ''



export default {
    data() {
        return {
            users,
            isShow
            ,inputValue
        };
    },
    methods: {
        handleShowData() {
            this.isShow = !this.isShow
        },
        handleDeleteData(id){
            console.log(id)
            users.splice(id,1)
            console.log(users)
        },
        handleChangeInput(e){
            console.log(e.target.value)
        }
    },
    components: {
        MenuItemView
    }
}
</script>

<template>
  <div class="home">
    <button @click="handleShowData" class="btn-show">Show data</button>
    <div class="user-data" v-if="isShow">
        <div class="user-item" v-for="(user,index) in users" :key="index">
            <div class="user-name">Ten: {{ user.name }}</div>
            <div class="user-age">Tuoi: {{ user.age }}</div>
            <button class="btn-delete" @click="handleDeleteData(index)">Delete</button>
        </div>
    </div>
    <input type="text" name="" id="" @input="handleChangeInput" :value="inputValue">
    <div class="list-item">
        <Teleport to = 'body'>
            <MenuItemView v-for="(user,index) in users" :key="index" :datas = "user" title-test ='xin chaoo' theme = 'light' />
        </Teleport>
    </div>
  </div>
</template>
