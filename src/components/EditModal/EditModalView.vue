<script>
import './EditModalView.scss'

export default {
  props: {
    data: Object,
  },
  emits: [],
  data() {
    return {
        
    }
  },
  methods: {
   
  }
}
</script>

<template>
    <Teleport to="body">
        <div class="modal">
            <div class="modal-content">
                <p>Sửa thông tin user</p>
                <div class="modal-item">
                    <label for="">Tên: </label>
                    <input type="text" name="" id="name" placeholder="Nhập tên...">
                </div>
                <div class="modal-item">
                    <label for="">Tuổi: </label>
                    <input type="text" name="" id="name" placeholder="Nhập tuổi...">
                </div>
                <button>Sửa</button>
            </div>
        </div>
    </Teleport>
</template>


