<script>
import EditModalView from '../EditModal/EditModalView.vue'
import '../MenuItem/MenuItemView.scss'

export default {
    props: {
        datas: Object,
    },
    emits: ["edit-user", "delete-user"],
    data() {
        return {};
    },
    methods: {
        editUser() {
            this.$emit("edit-user");
        },
        deleteUser() {
            this.$emit("delete-user");
        }
    },
    components: { EditModalView }
}
</script>

<template>
  <div class="item">
    <div class="item-data">
      <div> Tên: {{ datas.name }}</div>
      <div> Tuổi: {{ datas.age }}</div>
    </div>
    <div class="item-action">  
      <button @click="editUser">Sửa</button>
      <button @click="deleteUser">Xóa</button>
    </div>
  </div>
</template>


