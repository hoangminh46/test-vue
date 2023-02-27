<script>
import './HomeView.scss'
import MenuItemView from '../../components/MenuItem/MenuItemView.vue'
import EditModalView from '../../components/EditModal/EditModalView.vue'

const users = [
  { name: 'minh', age: 20 },
  { name: 'long', age: 22 },
  { name: 'nam', age: 21 }
]

const isShowData = true
const isShowModal = false
const inputAgeValue = ''
const inputNameValue = ''

export default {
  data() {
    return {
      users,
      isShowData,
      isShowModal,
      inputNameValue,
      inputAgeValue
    }
  },
  methods: {
    handleShowData() {
      this.isShowData = !this.isShowData
    },
    handleDeleteUser(id) {
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
    },
    handleEditUser (user){
        this.isShowModal = !this.isShowModal
        console.log(user)
    }
  },
  components: {
    MenuItemView,
    EditModalView
    }
}

</script>

<template>
  <div class="home">
    <button @click="handleShowData" class="btn-show">Hiển thị dữ liệu</button>
    <div class="add-user" v-if="isShowData">
        <p>Thêm user</p>
        <input type="text" v-model="inputNameValue" placeholder="Nhập tên" />
        <input type="text" v-model.number="inputAgeValue" placeholder="Nhập tuổi" />
        <button class="add-btn" @click="handleAddUser(inputNameValue, inputAgeValue)">Thêm</button>
    </div>
    <div class="user-data" v-if="isShowData">
        <MenuItemView
          v-for="(user, index) in users"
          :datas="user"
          @delete-user="handleDeleteUser"
          @edit-user="handleEditUser(user)"
        />
    </div>
    <EditModalView v-if="isShowModal"/>
  </div>
</template>
