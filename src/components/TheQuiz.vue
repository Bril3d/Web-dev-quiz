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
    background: #88272c;
    color: #f0f6fc;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 20px;
    padding: 10px;
    width: 500px;
    height: 500px;
    
}
@media (max-width:516px) {
.container {
    width: 290px;
    height: 300px;
}
}

</style>