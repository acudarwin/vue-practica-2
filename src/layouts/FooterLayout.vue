<template lang="">
    <footer id="app-footer" :style="{'background-color': footerColor}">
        
    </footer>
</template>
<script>
export default {
    setup() {
        return {
            footerColor: "slategrey",
        }
    }
}
</script>
<style lang="css">
    footer {
                
        text-align: center;
        padding: 30px 10px;
        margin-top: 50px;
        min-height: 100px;
    }
</style>