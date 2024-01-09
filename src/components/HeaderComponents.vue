<template>
    <header class="header">
        <div class="flex align-center">
            <h2 class="header-title">Calcomaniacos</h2>
        </div>
        <nav class="header-nav">
            <ul>
                <li><a href="#">Crear tu colección</a></li>
                <li><a href="#">Comprar stickers</a></li>
                <li><a href="#">Galeria</a></li>
                <li><a href="#">Contacto</a></li>
            </ul>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'HeaderComponents',
}
</script>

<style>
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 70px;
    background-color: #fa9c09;
    padding: 0 1rem;
    z-index: 100;
}

.header-title {
    font-size: 24px;
    margin: 0;
}

.header-nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.header-nav ul li {
    display: inline-block;
    margin-right: 10px;
}
.header-nav ul li a {
    color: inherit;
    text-decoration: none;
}
</style>
