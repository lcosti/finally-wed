<template>
    <div class="thanks">
        <h2>Will you be using the adult or children's menu?</h2>
        <div class="menu form flex row">
        <label class="input-item">
        <p>Adult</p>
        <input type="radio" @change="updateMenuType" name="guestAge" value="adult">
        </label>
        <label class="input-item">
        <p>Childrens</p>
        <input type="radio" @change="updateMenuType" name="guestAge" value="child">
        </label>
        </div>
        <slot></slot>
    </div>
</template>
<script>
import { useOptionsStore } from "../../stores/optionsStore"
export default{
      setup() {
        const optionsStore = useOptionsStore()
        return { optionsStore }
    },
    methods: {
        updateMenuType(e){
            this.optionsStore.updatedMenuType(e.target.value)
        },
    }
}
</script>
<style lang="scss">
.thanks{
    text-align: center;
    h2{
        margin-bottom: 1rem;
    }
    .menu{
        justify-content: center;
        font-size: 1.2rem;
    }
}
</style>