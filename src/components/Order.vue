<template>
    <div>

        <header class="header">
            <div class="logo">
                <img src="../img/icons/logo.svg" alt="logo">
            </div>
        </header>

        <div class="wrapper order">

            <div class="container">

                <h1 class="order__title">
                    Персональные данные
                </h1>

                <p class="order__text">
                    Укажите ваши данные, для завершения формирования заказа
                </p>

                <form class="form-group">

                    <div class="form-group__items-wrapper">
                        <div class="form-group__item">

                            <label class="form-group__label">Имя</label>

                            <input type="text" class="form-group__input" placeholder="Елена">

                        </div>

                        <div class="form-group__item">

                            <label class="form-group__label">Фамилия</label>

                            <input type="text" class="form-group__input" placeholder="Иванова">

                        </div>
                    </div>

                    <div class="form-group__items-wrapper">
                        <div class="form-group__item">

                            <label class="form-group__label">Телефон</label>

                            <input type="tel" class="form-group__input" placeholder="+7 (000) 000-00-00">

                            <div class="form-group__text">
                                По нему с вами свяжется менеджер для подтверждения заказа
                            </div>
                        </div>
                    </div>

                    <div class="form-group__items-wrapper">
                        <div class="form-group__item">

                            <label class="form-group__label">E-mail</label>

                            <input type="email" class="form-group__input" placeholder="mail@mail.com">

                            <div class="form-group__text">
                                На него мы отправим информацию и статус заказа
                            </div>
                        </div>
                    </div>



                </form>

            </div>

        </div>

    </div>
</template>

<script>
    export default {
        name: "Order"
    }
</script>

<style scoped>

</style>