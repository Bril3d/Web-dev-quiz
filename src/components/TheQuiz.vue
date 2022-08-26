<template>
   <div class="container">
        <header>
            <slot name="header"></slot>
        </header>
        <main>
            <slot name="main"></slot>
        </main>
        <footer>
            <slot name="footer"></slot>
        </footer>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.container {
    background: #30363d;
    color: #f0f6fc;
    box-shadow: 1px 1px 5px 0 #f0f6fc;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 20px;
    padding: 20px;
    width: 300px;
    height: 500px;
    
}

</style>