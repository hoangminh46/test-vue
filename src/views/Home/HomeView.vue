<script>
import './HomeView.scss'
import MenuItemView from '../../components/MenuItem/MenuItemView.vue'

const users = [
  { name: 'minh', age: 20 },
  { name: 'long', age: 22 },
  { name: 'nam', age: 21 }
]

const isShow = true
const inputAgeValue = ''
const inputNameValue = ''

export default {
  data() {
    return {
      users,
      isShow,
      inputNameValue,
      inputAgeValue
    }
  },
  methods: {
    handleShowData() {
      this.isShow = !this.isShow
    },
    handleDeleteData(id) {
      this.users.splice(id, 1)
      console.log(this.users)
    },
    handleAddUser(name, age) {
      const newDataUser = {
        name: name,
        age: age
      }
      this.users.push(newDataUser)
      console.log(this.users)
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
    <input type="text" v-model="inputNameValue" placeholder="Nhập tên" />
    <input type="text" v-model.number="inputAgeValue" placeholder="Nhập tuổi" />
    {{ inputNameValue }}
    {{ inputAgeValue }}
    <button class="add-btn" @click="handleAddUser(inputNameValue, inputAgeValue)">Thêm</button>
    <div class="user-data" v-if="isShow">
      <div class="user-item" v-for="(user, index) in users" :key="index">
        <div class="user-name">Ten: {{ user.name }}</div>
        <div class="user-age">Tuoi: {{ user.age }}</div>
        <button class="btn-delete" @click="handleDeleteData(index)">Delete</button>
      </div>
    </div>
    <!-- <div class="list-item">
      <Teleport to="body">
        <MenuItemView
          v-for="(user, index) in users"
          :key="index"
          :datas="user"
          title-test="xin chaoo"
          theme="light"
        />
      </Teleport>
    </div> -->
  </div>
</template>
