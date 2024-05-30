<template>
    <header>
        <div class="container-header">
            <div class="row-header">

                <div class="header-left">
                    a<span>Donna</span>
                    <span>Uomo</span>
                    <span>Bambini</span>
                </div>
                <div class="header-center">
                    <img class="icona-logo" src="../img/boolean-logo.png">
                </div>
                <div class="header-right">
                    <img class="icone" src="https://img.icons8.com/forma-thin/24/user.png" >
                    <img class="icone" src="https://img.icons8.com/ios/50/like--v1.png">
                    <img class="icone" src="https://img.icons8.com/ios-filled/50/shopping-bag.png">
                </div>
            </div>
            </div>
    </header>
</template>

<script>
    export default {
    name: "headers"
};
</script>
<style scoped>
    .container-header{
        width: 100%;
        margin: auto;
        padding: 10px;
    }
    .row-header{
        display: flex;
        flex-wrap: wrap;
        align-items: center;
    }
    .header-left{
    width: 30%;
    display: flex;
    justify-content: center;
    gap: 5px;
    }
    .header-center{
    width: 40%;
    display: flex;
    justify-content: center;
    }
    .header-right{
    width: 30%;
    display: flex;
    justify-content: center;
    gap: 5px;
    }
    .icone{
    height: 20px;
    width: 20px;
}
.icona-logo{
    width: 150px;
    height: 50px;
}
</style>