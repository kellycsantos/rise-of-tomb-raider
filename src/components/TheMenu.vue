<template>
    <button class="hamburger-icon" @click="openMenu">

    </button>
    <div class="menu">
        <ul class="menu-list" :class="open ? '' : 'menu-list-close'" >
            <li><a href="#home">Início</a></li>
            <li><a href="#story">História</a></li>
            <li class="logo">
                <a class="menu-item-logo" href="#home">
                    <h4>rise of the</h4>
                    <h2>tomb raider</h2>
                </a>
            </li>
            <li><a href="#resume">Sinopse</a></li>
            <li><a href="#release">Lançamento</a></li>

        </ul>
    </div>
</template>
<script>
export default ({
    data() {
        return {
            open: false,
            teste: window.screen.width,
        }
    },
    methods: {
        openMenu() {
            this.open = !this.open
        }
    }
})
</script>
<style scoped>
* {
    list-style: none;
    text-decoration: none;
    outline: none;
    border: none;
}

a {
    color: #f2f2f2;
}

.hamburger-icon {
    background: url('https://static.thenounproject.com/png/4615397-200.png') center no-repeat;
    width: 60px;
    height: 50px;
    background-size: 70px;
    position: absolute;
    top: 10px;
    left: 10px;
}

.menu {
    background: #302f2e9a;
    display: flex;
    justify-content: space-between;

}

.logo {
    display: none;
}

.menu-list {
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-direction: column;
    width: 100vw;
    padding: 20px 10vw;
    font-size: x-large;
}

.menu-list-close{
    display: none;
}
.menu-list li {
    margin: 10px 0;
}



@media screen and (min-width:768px) {
    .logo {
        display: block;

    }

    .menu-list{
        flex-direction: row;
    }

    .menu-list-close{
        display: flex;
    }

    .menu-item-logo {
        text-transform: uppercase;
        display: flex;
        flex-direction: column;
        display: block;
    }

    .menu-item-logo h4 {
        color: #64000d;
        text-align: center;
        word-spacing: 30px;
        display: inline-block;

    }
    .hamburger-icon{
        display: none;
    }

}
</style>