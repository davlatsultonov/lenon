<template>
    <div>

        <header class="header">
            <div class="logo">
                <img src="../img/icons/logo.svg" alt="logo">
            </div>
        </header>

        <div class="wrapper order">

            <div class="container">

                <h1 class="order__title margin-top-15">
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

            <div class="container">

                <h1 class="order__title">
                    Как будем доставлять заказ?
                </h1>

                <form class="form-group">

                    <div class="form-group__items-wrapper">
                        <div class="form-group__item">
                            <label class="form-group__radio">Самовывоз Адрес: Омск, ул. Ленина 14/1, 3 этаж, офис 312
                                <input type="radio" checked="checked" name="radio">
                                <span class="checkmark"></span>
                            </label>
                            <label class="form-group__radio">Доставка Почтой России
                                <input type="radio" name="radio">
                                <span class="checkmark"></span>
                            </label>
                            <label class="form-group__radio">Доставка СДЭК
                                <input type="radio" name="radio">
                                <span class="checkmark"></span>
                            </label>
                        </div>
                    </div>

                    <div class="form-group__items-wrapper">
                        <div class="form-group__item form-group__item_lg">
                            <label class="form-group__label">Адрес доставки</label>

                            <input type="text" class="form-group__input" placeholder="Начните вводить адрес">
                        </div>
                    </div>

                    <div class="form-group__items-wrapper">
                        <div class="form-group__item form-group__item_lg">
                            <label class="form-group__label">Комментарий</label>

                            <textarea class="form-group__comments" placeholder="Особые указания для доставки?"></textarea>

                            <div class="form-group__text">
                                Стоимость доставки наш менеджер сообщит сразу после подтверждения заказа
                            </div>
                        </div>
                    </div>



                </form>

            </div>

            <div class="container">

                <h1 class="order__title">
                    Оплата сразу?
                </h1>

                <form class="form-group">
                    <div class="form-group__items-wrapper">
                        <div class="form-group__item">
                            <label class="form-group__radio">Безналичным способом
                                <input type="radio" checked="checked" name="radio-2">
                                <span class="checkmark"></span>
                            </label>
                            <label class="form-group__radio">Оплата при получении (наличными или картой)
                                <input type="radio" name="radio-2">
                                <span class="checkmark"></span>
                            </label>
                        </div>
                    </div>
                </form>

            </div>

            <div class="container">
                <footer class="footer">

                    <div class="footer__column">
                        <div class="option-block">

                            <div class="option-block__title option-block__title_lg footer__total-result">
                                Итого: <span>5 000 руб.</span>
                            </div>

                            <div class="footer__note">
                                Цена не включается в себя стоимость доставки
                            </div>

                        </div>
                    </div>

                    <div class="footer__column footer__column_md">

                        <div class="btn-group footer__btn-group">

                            <a href="#" class="btn-group__item btn-group__item_result">
                                Вернуться назад
                            </a>

                            <a href="#" class="btn-group__item btn-group__item_result btn-group__item_result-dark">
                                Подтвердить
                            </a>

                        </div>

                    </div>


                </footer>
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