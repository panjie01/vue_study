<template>
    <li class="cs">
        <input type="checkbox" v-model="checked"/> 
        <!-- <slot name="st">{{item}}</slot> -->
        <!-- <slot name="st"></slot> -->
        <slot name="st" v-bind="{checked}"></slot>
    </li>
</template>
<script>
    export default {
        props:['item'], //声明能接受的参数（属性）
        data() {
            return{
                checked:false
            }
        }
    }
</script>
<style>
    .cs {
            color: red;
        }

</style>
