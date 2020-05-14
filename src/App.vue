<template>

    <div>

        <header class="header">
            <div class="logo">
                <img src="./assets/images/icons/logo.svg" alt="logo">
            </div>
        </header>

        <div class="wrapper">
            <div class="container padding-top-30">

                <div class="container__column">
                    <div class="product-slider">

                        <div class="product-slider__item product-slider__item_upper">
                            <VueSlickCarousel :arrows="true" :fade="true" :infinite="true">
                                <div class="product-slider__img"><img src="./assets/images/upper-part.png"/></div>
                                <div class="product-slider__img"><img src="./assets/images/upper-white.png"/></div>
                            </VueSlickCarousel>
                        </div>

                        <div class="product-slider__item product-slider__item_lower">
                            <VueSlickCarousel :arrows="true" :fade="true">
                                <div class="product-slider__img">
                                    <div style="width: 100%; height: 100%; background-color: #353228"></div>
                                </div>
                                <div class="product-slider__img"><img src="./assets/images/lower-part.png"/></div>
                            </VueSlickCarousel>
                        </div>

                        <div class="product-slider__separater">
                            <img src="./assets/images/slider-line.svg" alt="slider-line">
                        </div>

                        <button type="button" class="product-slider__expand-btn">
                            <img src="./assets/images/icons/expand-icon.svg" alt="expand-icon">
                        </button>
                    </div>
                </div>

                <div class="container__column margin-right-0">

                    <div class="option-block">

                        <div class="option-block__title padding-top-5">
                            Выберите фасон
                        </div>

                        <div class="option-block__content">

                            <div class="product-style">
                                <div class="product-style__items">

                                    <div class="product-style__item">
                                        <button class="product-style__btn active">
                                            <img class="product-style__icon" src="./assets/images/icons/straight.svg"
                                                 alt="straight-icon">
                                        </button>
                                        <div class="product-style__text">Прямое</div>
                                    </div>

                                    <div class="product-style__item">
                                        <button class="product-style__btn">
                                            <img class="product-style__icon" src="./assets/images/icons/trapezoid.svg"
                                                 alt="trapezoid-icon">
                                        </button>
                                        <div class="product-style__text">Трапеция</div>
                                    </div>

                                    <div class="product-style__item">
                                        <button class="product-style__btn">
                                            <img class="product-style__icon" src="./assets/images/icons/cutting.svg"
                                                 alt="cutting-icon">
                                        </button>
                                        <div class="product-style__text">Отрезное</div>
                                    </div>

                                </div>
                            </div>

                            <div class="option-block__title">
                                Выберите цвет
                            </div>


                            <!--<div class="color-picker color-picker__container">
                                <span class="color-picker__item checked" style="background-color: #c4867b"></span>
                            </div>-->
                            <ul class="color-picker color-picker__container">
                                <li class="color-picker__item checked" style="background-color: #c4867b"></li>
                                <li class="color-picker__item" style="background-color: #FA6400"></li>
                                <li class="color-picker__item" style="background-color: #8A2220"></li>
                                <li class="color-picker__item" style="background-color: #A2522F"></li>
                                <li class="color-picker__item" style="background-color: #C4867B"></li>
                                <li class="color-picker__item" style="background-color: #C38120"></li>
                                <li class="color-picker__item" style="background-color: #365130"></li>
                                <li class="color-picker__item" style="background-color: #004C4B"></li>
                                <li class="color-picker__item" style="background-color: #004C4B"></li>
                                <li class="color-picker__item" style="background-color: #154F90"></li>
                                <li class="color-picker__item" style="background-color: #5989B9"></li>
                                <li class="color-picker__item" style="background-color: #F3F4F5"></li>
                                <li class="color-picker__item" style="background-color: #C8C7C0"></li>
                            </ul>


                            <div class="option-block__title">
                                Выберите цвет
                            </div>

                            <ul class="color-picker color-picker__container">
                                <li class="color-picker__item checked" style="background-color: #c4867b"></li>
                                <li class="color-picker__item" style="background-color: #FA6400"></li>
                                <li class="color-picker__item" style="background-color: #8A2220"></li>
                                <li class="color-picker__item" style="background-color: #A2522F"></li>
                                <li class="color-picker__item" style="background-color: #C4867B"></li>
                                <li class="color-picker__item" style="background-color: #C38120"></li>
                                <li class="color-picker__item" style="background-color: #365130"></li>
                                <li class="color-picker__item" style="background-color: #004C4B"></li>
                                <li class="color-picker__item" style="background-color: #004C4B"></li>
                                <li class="color-picker__item" style="background-color: #154F90"></li>
                                <li class="color-picker__item" style="background-color: #5989B9"></li>
                                <li class="color-picker__item" style="background-color: #F3F4F5"></li>
                                <li class="color-picker__item" style="background-color: #C8C7C0"></li>
                            </ul>

                            <div class="option-block__title">
                                Выберите принт верха
                            </div>

                            <div class="btn-group padding-top-13">
                                <div class="btn-group__items">
                                    <button type="button" class="btn-group__item btn-group__item_sm active">
                                        Без принта
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_sm">
                                        До пояса
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_sm">
                                        Полностью
                                    </button>
                                </div>
                            </div>

                            <div class="product-style product-style_patterns">
                                <div class="product-style__item">
                                    <button class="product-style__btn active">
                                        <img class="product-style__icon" src="./assets/images/icons/pattern.svg"
                                             alt="pattern-icon">
                                    </button>
                                </div>

                                <div class="product-style__item">
                                    <button class="product-style__btn">
                                        <img class="product-style__icon" src="./assets/images/icons/pattern.svg"
                                             alt="pattern-icon">
                                    </button>
                                </div>

                                <div class="product-style__item">
                                    <button class="product-style__btn">
                                        <img class="product-style__icon" src="./assets/images/icons/pattern.svg"
                                             alt="pattern-icon">
                                    </button>
                                </div>

                                <div class="product-style__item">
                                    <button class="product-style__btn">
                                        <img class="product-style__icon" src="./assets/images/icons/pattern.svg"
                                             alt="pattern-icon">
                                    </button>
                                </div>

                                <div class="product-style__item">
                                    <button class="product-style__btn">
                                        <img class="product-style__icon" src="./assets/images/icons/pattern.svg"
                                             alt="pattern-icon">
                                    </button>
                                </div>

                                <div class="product-style__item">
                                    <button class="product-style__btn">
                                        <img class="product-style__icon" src="./assets/images/icons/pattern.svg"
                                             alt="pattern-icon">
                                    </button>
                                </div>

                                <div class="product-style__item">
                                    <button class="product-style__btn">
                                        <img class="product-style__icon" src="./assets/images/icons/pattern.svg"
                                             alt="pattern-icon">
                                    </button>
                                </div>


                                <div class="product-style__item">
                                    <div class="product-style__btn product-style__link">
                                        <a href="#">еще <span>+10</span></a>
                                    </div>
                                </div>
                            </div>

                        </div>


                    </div>


                </div>

                <div class="product-note">
                    <div class="product-note__items">
                        <div class="product-note__icon">
                            <img src="./assets/images/icons/bell.svg" alt="bell-icon">
                        </div>

                        <div class="product-note__description">
                            Оптимально цвет принта совпадает с выбранным цветом юбки. Если платье однотонное, мы красим
                            принт в
                            наш базовый цвет. Если хотите индивидуальный цвет принта, напишите нам в комментарий к
                            заказу.
                        </div>
                    </div>
                </div>


            </div>

            <div class="container">

                <div class="container__column">
                    <div class="option-block">

                        <div class="option-block__title">
                            Выберите размер
                        </div>

                        <div class="option-block__content">

                            <div class="btn-group">
                                <div class="btn-group__items">
                                    <button type="button" class="btn-group__item btn-group__item_sm active">
                                        Взрослое
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_sm">
                                        Детское
                                    </button>
                                </div>
                            </div>

                            <div class="option-block__title option-block__title_xs">
                                Евро размер

                                <info-popover></info-popover>

                                <size-popover></size-popover>

                            </div>

                            <div class="btn-group">
                                <div class="btn-group__items">
                                    <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                        xs
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                        s
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                        m
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                        l
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                        xl
                                    </button>
                                </div>
                            </div>

                            <div class="option-block__title option-block__title_xs">
                                Ваш рост

                                <info-popover></info-popover>
                            </div>

                            <div class="btn-group">
                                <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                    150
                                </button>

                                <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                    160
                                </button>

                                <button type="button" class="btn-group__item btn-group__item_xs active">
                                    170
                                </button>

                                <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                    180
                                </button>

                                <button type="button" class="btn-group__item btn-group__item_xs disabled">
                                    190
                                </button>
                            </div>

                            <div class="product-note">

                                <div class="product-note__description">
                                    Мы подберем подходящую длину по нашему стандарту
                                </div>

                            </div>
                        </div>

                    </div>
                </div>

                <div class="container__column">
                    <div class="option-block">

                        <div class="option-block__title">
                            или укажите свои мерки
                        </div>

                        <div class="option-block__content">

                            <div class="product-note margin-bottom-12">
                                <div class="product-note__description">
                                    Мы изготовим платье по вашим меркам. Есть видео-инструкция с рекомендациями, если
                                    возниктнут
                                    вопросы.

                                    <video-popover></video-popover>
                                </div>
                            </div>

                            <div class="input-group">
                                <div class="input-group__container input-group__container_md">
                                    <div class="option-block__title option-block__title_xs">
                                        Длина платья до талии
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см">
                                </div>

                                <div class="input-group__container input-group__container_md">
                                    <div class="option-block__title option-block__title_xs">
                                        Длина всего платья от плеча
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см">
                                </div>
                            </div>

                            <div class="input-group">
                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват груди
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см">
                                </div>

                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват талии
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см">
                                </div>

                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват бедер
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см">
                                </div>

                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват руки
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см">
                                </div>
                            </div>

                            <div class="product-note">
                                <div class="product-note__description">
                                    <a href="#">Сбросить показатели</a> если хотите выбрать стандартный размер
                                </div>
                            </div>


                        </div>

                    </div>
                </div>

            </div>

            <div class="container">

                <div class="container__column">
                    <div class="option-block">

                        <div class="option-block__title">
                            Выберите дополнительно
                        </div>

                        <div class="option-block__content">

                            <div class="btn-group">
                                <div class="option-block__title option-block__title_sm">
                                    Пуговки
                                </div>

                                <div class="btn-group__items">
                                    <button type="button" class="btn-group__item btn-group__item_sm active">
                                        На груди
                                    </button>

                                    <button type="button" class="btn-group__item btn-group__item_sm">
                                        На спине
                                    </button>

                                    <div class="btn-group">

                                        <button type="button" class="btn-group__item ">

                                            До талии

                                            <popover></popover>
                                        </button>

                                        <button type="button" class="btn-group__item ">
                                            Всю длину
                                            <popover></popover>
                                        </button>
                                        <info-popover></info-popover>
                                    </div>

                                    <div class="option-block__title option-block__title_sm">
                                        Воротник
                                    </div>

                                    <button type="button" class="btn-group__item ">
                                        Стойка

                                        <popover></popover>
                                    </button>

                                    <button type="button" class="btn-group__item ">
                                        Английский

                                        <popover></popover>
                                    </button>

                                    <div class="option-block__title option-block__title_sm">
                                        Рукава
                                    </div>

                                    <button type="button" class="btn-group__item ">
                                        3/4

                                        <popover></popover>
                                    </button>

                                    <button type="button" class="btn-group__item ">
                                        Стандартные

                                        <popover></popover>
                                    </button>

                                    <div class="option-block__title option-block__title_sm">
                                        Завязки (пояс)
                                    </div>

                                    <button type="button" class="btn-group__item ">
                                        В боковых швах

                                        <popover></popover>
                                    </button>

                                    <div class="option-block__title option-block__title_sm">
                                        Карманы
                                    </div>

                                    <button type="button" class="btn-group__item ">
                                        В боковых швах

                                        <popover></popover>
                                    </button>
                                </div>
                            </div>

                        </div>

                    </div>
                </div>

                <div class="container__column">

                    <div class="option-block__title">
                        Так же можно добавить
                    </div>

                    <div class="option-block__content">

                        <div class="btn-group">
                            <div class="btn-group__items">
                                <button type="button" class="btn-group__item">
                                    Декоративный кармашек

                                    <popover></popover>
                                </button>

                                <button type="button" class="btn-group__item">
                                    Поясок

                                    <popover>
                                        <template #slide-items>
                                            <div class="product-slider__img"><img src="./assets/images/popover-img.png"/></div>
                                            <div class="product-slider__img"><img src="./assets/images/upper-part.png"/></div>
                                        </template>
                                    </popover>
                                </button>

                            </div>

                            <div class="btn-group__items">
                                <button type="button" class="btn-group__item">
                                    Молния для кормления

                                    <popover></popover>
                                </button>

                                <button type="button" class="btn-group__item">
                                    Шопер

                                    <popover>
                                        <template #slide-items>
                                            <div class="product-slider__img"><img src="./assets/images/popover-img.png"/></div>
                                            <div class="product-slider__img"><img src="./assets/images/upper-part.png"/></div>
                                        </template>
                                    </popover>
                                </button>

                            </div>

                            <div class="btn-group__items">
                                <button type="button" class="btn-group__item">
                                    Кармашек с вышивкой

                                    <popover></popover>
                                </button>

                                <button type="button" class="btn-group__item">
                                    Кардиган

                                    <popover>
                                        <template #slide-items>
                                            <div class="product-slider__img"><img src="./assets/images/popover-img.png"/></div>
                                            <div class="product-slider__img"><img src="./assets/images/upper-part.png"/></div>
                                        </template>
                                    </popover>
                                </button>

                            </div>

                            <div class="btn-group__items">
                                <button type="button" class="btn-group__item">
                                    Резинки для волос

                                    <popover></popover>
                                </button>

                                <button type="button" class="btn-group__item">
                                    Нижняя юбка

                                    <popover>
                                        <template #slide-items>
                                            <div class="product-slider__img"><img src="./assets/images/popover-img.png"/></div>
                                            <div class="product-slider__img"><img src="./assets/images/upper-part.png"/></div>
                                        </template>
                                    </popover>
                                </button>

                            </div>

                        </div>

                        <div class="product-note margin-top-6">
                            <div class="product-note__description">
                                Предложенные товары выше добавлять не обязательно, но возможно, то что мы можем
                                изготовить
                                дополнительно, Вам пригодится.
                            </div>
                        </div>

                    </div>

                </div>
            </div>

            <div class="container">

                <div class="container__column container__column_fluid">
                    <div class="option-block">

                        <div class="option-block__title option-block__title_lg">
                            Ваше платье
                        </div>

                        <div class="option-block__content">

                            <div class="container__column container__column_sm">

                                <div class="selection-result">
                                    <div class="option-block__title selection-result__title">
                                        Базовые свойства
                                    </div>

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item">Фасон:</li>
                                            <li class="result-list__item">Цвет верха:</li>
                                            <li class="result-list__item">Цвет юбки:</li>
                                            <li class="result-list__item">Принт:</li>
                                            <li class="result-list__item">Цвет принта:</li>
                                            <li class="result-list__item">Размер:</li>
                                            <li class="result-list__item">Длина платья:</li>
                                        </ul>
                                    </div>

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item">Прямое</li>
                                            <li class="result-list__item">
                                                Графитовый
                                                <span class="result-list__item_color"></span>
                                            </li>
                                            <li class="result-list__item">Горчичный</li>
                                            <li class="result-list__item">Без принта</li>
                                            <li class="result-list__item unselected">–</li>
                                            <li class="result-list__item">Выберите размер</li>
                                            <li class="result-list__item">–</li>
                                        </ul>
                                    </div>
                                </div>

                            </div>

                            <div class="container__column container__column_md">

                                <div class="selection-result">

                                    <div class="option-block__title selection-result__title">
                                        Индивидуальные размеры
                                    </div>

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item">Длина платья до талии:</li>
                                            <li class="result-list__item">Длина всего платья от плеча:</li>
                                            <li class="result-list__item">Обхват груди:</li>
                                            <li class="result-list__item">Обхват талии:</li>
                                            <li class="result-list__item">Обхват бедер:</li>
                                            <li class="result-list__item">Обхват руки:</li>
                                        </ul>
                                    </div>

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item">60 см</li>
                                            <li class="result-list__item">180 см</li>
                                            <li class="result-list__item">92 см</li>
                                            <li class="result-list__item">60 см</li>
                                            <li class="result-list__item">60 см</li>
                                            <li class="result-list__item">–</li>
                                        </ul>
                                    </div>
                                </div>

                            </div>

                            <div class="container__column container__column_sm">

                                <div class="product-note margin-bottom-12 margin-top-55">
                                    <div class="product-note__description">
                                        Проверьте внимательно указанные размеры перед окончательным оформлением заказа.
                                        Если сомневаетесь есть видео-инструкция с рекомендациями

                                        <div class="column-link_bottom">
                                            <video-popover></video-popover>
                                        </div>
                                    </div>
                                </div>

                            </div>

                        </div>

                        <div class="option-block__title option-block__title_bold margin-bottom-15">
                            Цена платья: <span>5 000</span> руб.
                        </div>

                        <div class="option-block__content">

                            <div class="option-block__title">
                                Дополнительно вы выбрали
                            </div>

                           <!-- <div class="option-block__title option-block__title_sm unselected padding-top-17 padding-bottom-17">
                                Выберите аксессуары и фурнитуру дополнительно к платью выше.
                            </div>-->

                            <div class="selection-result">

                                <div class="selection-result_wrapper">

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item">Пуговки</li>
                                            <li class="result-list__item">Рукава</li>
                                            <li class="result-list__item">Карманы</li>
                                        </ul>
                                    </div>

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item">300 руб.</li>
                                            <li class="result-list__item">300 руб.</li>
                                            <li class="result-list__item">300 руб.</li>
                                        </ul>
                                    </div>

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item">На груди, 3/4</li>
                                            <li class="result-list__item">Да, 3/4</li>
                                            <li class="result-list__item">Да</li>
                                        </ul>
                                    </div>

                                    <div class="selection-result__column">
                                        <ul class="result-list">
                                            <li class="result-list__item result-list__item_remove">
                                                Убрать
                                            </li>
                                            <li class="result-list__item result-list__item_remove">
                                                Убрать
                                            </li>
                                            <li class="result-list__item result-list__item_remove">
                                                Убрать
                                            </li>
                                        </ul>
                                    </div>


                                </div>

                            </div>

                            <div class="option-block__title option-block__title_bold">
                                Цена всех дополнений: 0 руб.
                            </div>


                        </div>


                    </div>
                </div>
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
                                Отправить на e-mail
                            </a>

                            <a href="#" class="btn-group__item btn-group__item_result btn-group__item_result-dark">
                                Добавить в корзину
                            </a>

                        </div>

                    </div>


                </footer>
            </div>

        </div>

    </div>

</template>


<script>
    import VueSlickCarousel from 'vue-slick-carousel'
    import InfoPopover from './components/InfoPopover'
    import VideoPopover from './components/VideoPopover'
    import SizePopover from './components/SizePopover'
    import Popover from './components/Popover'


    export default {
        name: 'App',
        components: {
            VueSlickCarousel,
            'popover': Popover,
            'size-popover': SizePopover,
            'info-popover': InfoPopover,
            'video-popover': VideoPopover
        },
        data() {
            return {
                show: false,
                checked: true
            }
        },
        methods: {
            check() {
                this.checked = !this.checked;
            }
        }
    }


</script>
<style lang="scss">
    @import "./assets/styles/main";
</style>
