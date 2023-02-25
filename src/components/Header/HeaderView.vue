<script>
import { RouterLink, RouterView } from 'vue-router'
import './HeaderView.scss'
export default {
    data() {
        return {
            count: 0
        };
    }
    ,methods: {
        
    }
}
</script>

<template>
    <div class="header">
        <RouterLink to="/" class="header-link">Home</RouterLink>
        <RouterLink to="/about" class="header-link">About</RouterLink>
    </div>
</template>