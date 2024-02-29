<template>
    <nav class="navbar navbar-expand-lg head-navbar" style="background-color: #fff;">
        <div class="container">
            <a class="navbar-brand" href="#"><img class="apple-logo" src="../images/nb-logo.svg" alt="apple-logo"
                    width="40px" height="40px"></a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link" href="#">Продукция</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Стать партнером</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">О проекте</a>
                    </li>
                </ul>
                <ul class="navbar-nav mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="cart-img nav-link" href="ссылка_на_корзину">
                            <img src="../images/nb-cart.svg" alt="cart" width="20px" height="20px">
                        </a>
                    </li>
                </ul>
                <form class="d-flex" role="search">
                    <img src="../images/nb-search.png" alt="search-btn">
                </form>

            </div>
        </div>
    </nav>
</template>
    
<style>
    .cart-img img {
        margin-bottom: 5px;
        margin-right: 5px;
    }
</style>