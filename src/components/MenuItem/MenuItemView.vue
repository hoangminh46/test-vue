<script>
import '../MenuItem/MenuItemView.scss'

export default {
    
    props:{
        datas : Object,
        titleTest: String
    },
    emits : {  

    },
    data() {
        return {
            
        };
    }
    ,methods: {
        
    }
}
</script>

<template>
    <div class="item" :class="{'bg-theme' : theme === 'light' }"  >
        <div>{{ datas.name }}</div>
        <div>{{ titleTest }}</div>
    </div>
</template>

