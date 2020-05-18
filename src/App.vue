<template>

    <div>

        <header class="header">
            <div class="logo">
                <img src="./img/icons/logo.svg" alt="logo">
            </div>
        </header>

        <div class="wrapper">
            <div class="container padding-top-30">

                <div class="container__column">
                    <div class="product-slider">

                        <div class="product-slider__item product-slider__item_upper">
                            <VueSlickCarousel :arrows="true" :fade="true" :infinite="true">
                                <div class="product-slider__img"><img src="./img/upper-part.png"/></div>
                                <div class="product-slider__img"><img src="./img/upper-white.png"/></div>
                            </VueSlickCarousel>
                        </div>

                        <div class="product-slider__item product-slider__item_lower">
                            <VueSlickCarousel :arrows="true" :fade="true">
                                <div class="product-slider__img">
                                    <div style="width: 100%; height: 100%; background-color: #353228"></div>
                                </div>
                                <div class="product-slider__img"><img src="./img/lower-part.png"/></div>
                            </VueSlickCarousel>
                        </div>

                        <div class="product-slider__separater">
                            <img src="./img/slider-line.svg" alt="slider-line">
                        </div>

                        <button type="button" class="product-slider__expand-btn">
                            <img src="./img/icons/expand-icon.svg" alt="expand-icon">
                        </button>
                    </div>
                </div>

                <div class="container__column margin-right-0">

                    <div class="option-block">

                        <div class="option-block__title padding-top-5 margin-top-0">
                            Выберите фасон
                        </div>

                        <div class="option-block__content">

                            <div class="product-style">
                                <div class="product-style__items">

                                    <div class="product-style__item"
                                         v-for="(fashion, index) in styles.dressFachion.types" :key="fashion + index">
                                        <button class="product-style__btn" :class="{ active: fashion === styles.dressFachion.currentType }"
                                                @click="styles.dressFachion.currentType = fashion">
                                            <img class="product-style__icon" :src="getImgUrl(fashion.src)"
                                                 alt="straight-icon">
                                        </button>
                                        <div class="product-style__text">{{ fashion.text }}</div>
                                    </div>
                                </div>
                            </div>

                            <div class="option-block__title option-block__title_m-top">
                                Выберите цвет верха
                            </div>

                            <ul class="color-picker color-picker__container">
                                <li class="color-picker__item" v-for="(color, index) in colorsPalette.colors"
                                    :key="index" :class="{ checked: color === colorsPalette.currentUpColor}">
                                    <span :style="{ 'background-color': color }"
                                          @click="colorsPalette.currentUpColor = color"></span>
                                </li>
                            </ul>

                            <div class="option-block__title option-block__title_m-top">
                                Выберите цвет юбки
                            </div>

                            <ul class="color-picker color-picker__container">
                                <li class="color-picker__item" v-for="(color, index) in colorsPalette.colors"
                                    :key="index" :class="{ checked: color === colorsPalette.currentSkirtColor}">
                                    <span :style="{ 'background-color': color }"
                                          @click="colorsPalette.currentSkirtColor = color"></span>
                                </li>
                            </ul>

                            <div class="option-block__title option-block__title_m-top">
                                Выберите принт верха
                            </div>

                            <div class="btn-group padding-top-7">

                                <div class="btn-group__item btn-group__item_sm"
                                     v-for="(print, index) in printType.types" :key="index">
                                    <button type="button" :class="{ active:  print === printType.currentType }"
                                            @click="printType.currentType = print">
                                        {{ print }}
                                    </button>
                                </div>

                            </div>


                            <div class="product-style  product-style_patterns">


                                    <div class="product-style__item" v-for="(pattern, index) in styles.patterns.type"
                                         :key="pattern + index">
                                        <button class="product-style__btn" :class="{ active: pattern === styles.patterns.currentType }"
                                                @click="styles.patterns.currentType = pattern">
                                                <img class="product-style__icon" :src="getImgUrl(pattern)"
                                                 >
                                        </button>
                                    </div>

                                    <div class="product-style__item">
                                        <div class="product-style__btn product-style__link">
                                            <a href="#" @click.prevent>еще <span>+10</span></a>
                                        </div>
                                    </div>


                            </div>

                        </div>


                    </div>


                </div>

                <div class="product-note">
                    <div class="product-note__items">
                        <div class="product-note__icon">
                            <img src="./img/icons/bell.svg" alt="bell-icon">
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

                                <div class="btn-group__item btn-group__item_sm" v-for="(type, index) in sizeType.types"
                                     :key="type + index">
                                    <button type="button" :class="{ active:  type === sizeType.currentType }"
                                            @click="sizeType.currentType = type">
                                        {{ type }}
                                    </button>
                                </div>

                            </div>

                            <div class="option-block__title option-block__title_xs">
                                Евро размер

                                <info-popover></info-popover>

                                <size-popover></size-popover>

                            </div>

                            <div class="btn-group">

                                <div class="btn-group__item btn-group__item_xs" v-for="(size, index) in euroSize.size"
                                     :key="size + index">
                                    <button type="button" :class="{ active:  size === euroSize.currentSize }"
                                            @click="euroSize.currentSize = size">
                                        {{ size }}
                                    </button>
                                </div>

                            </div>

                            <div class="option-block__title option-block__title_xs">
                                Ваш рост

                                <info-popover></info-popover>
                            </div>

                            <div class="btn-group">
                                <div class="btn-group__item btn-group__item_xs" v-for="(h, index) in bodyHeight.height"
                                     :key="index">
                                    <button type="button" :class="{ active: h === bodyHeight.currentHeigt }"
                                            @click="bodyHeight.currentHeigt = h">
                                        {{ h }}
                                    </button>
                                </div>
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

                                    <input type="text" class="input-group__item" placeholder="см"
                                           v-model.number="measures.waist">
                                </div>

                                <div class="input-group__container input-group__container_md">
                                    <div class="option-block__title option-block__title_xs">
                                        Длина всего платья от плеча
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см"
                                           v-model.number="measures.shoulder">
                                </div>
                            </div>

                            <div class="input-group">
                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват груди
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см"
                                           v-model.number="measures['chest-girth']">
                                </div>

                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват талии
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см"
                                           v-model.number="measures['waist-girth']">
                                </div>

                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват бедер
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см"
                                           v-model.number="measures['hip-girth']">
                                </div>

                                <div class="input-group__container input-group__container_xs">
                                    <div class="option-block__title option-block__title_xs">
                                        Обхват руки
                                    </div>

                                    <input type="text" class="input-group__item" placeholder="см"
                                           v-model.number="measures['hand-girth']">
                                </div>
                            </div>

                            <div class="product-note">
                                <div class="product-note__description">
                                    <a href="#" @click.prevent="resetMeasures">Сбросить показатели</a> если хотите
                                    выбрать стандартный размер
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

                                <div class="btn-group__item" v-for="(dressButton, index) in dressButtons.types"
                                     :key="dressButton.text + index">
                                    <button type="button" :class="{ active: dressButton === dressButtons.currentType}"
                                            @click="dressButtons.currentType = dressButton"
                                            :disabled="dressButton.isDisabled">
                                        {{ dressButton.text }}

                                        <popover>
                                            <template v-if="dressButton.hasPopover">
                                                <div class="product-slider__img"><img
                                                        src="./img/popover-img.png"/></div>
                                                <div class="product-slider__img"><img
                                                        src="./img/upper-part.png"/>
                                                </div>
                                            </template>
                                        </popover>

                                    </button>
                                    <info-popover v-if="dressButton.hasInfo"></info-popover>
                                </div>


                                <!--<div class="btn-group__item">
                                    <button type="button">
                                        На груди
                                        <popover></popover>
                                    </button>
                                </div>

                                <div class="btn-group__item">
                                    <button type="button">
                                        На спине
                                        <popover></popover>
                                    </button>
                                </div>

                                <br>

                                <div class="btn-group__item">
                                    <button type="button">
                                        3/4
                                        <popover></popover>
                                    </button>
                                </div>

                                <div class="btn-group__item">
                                    <button type="button">
                                        До талии
                                        <popover></popover>
                                    </button>
                                </div>

                                <div class="btn-group__item">
                                    <button type="button" class="disabled">
                                        Всю длину
                                        <popover></popover>
                                    </button>
                                    <info-popover></info-popover>
                                </div>-->

                                <div class="option-block__title option-block__title_sm">
                                    Воротник
                                </div>


                                <div class="btn-group__item" v-for="(collarItem, index) in collar.types"
                                     :key="collarItem.text + index">
                                    <button type="button" :class="{ active: collarItem === collar.currentType}"
                                            @click="collar.currentType = collarItem" :disabled="collarItem.isDisabled">
                                        {{ collarItem.text }}

                                        <popover>
                                            <template v-if="collarItem.hasPopover">
                                                <div class="product-slider__img"><img
                                                        src="./img/popover-img.png"/></div>
                                                <div class="product-slider__img"><img
                                                        src="./img/upper-part.png"/>
                                                </div>
                                            </template>
                                        </popover>

                                    </button>
                                    <info-popover v-if="collarItem.hasInfo"></info-popover>
                                </div>
                                <!--<div class="btn-group__item">
                                    <button type="button">
                                        Стойка
                                        <popover></popover>
                                    </button>
                                </div>
                                <div class="btn-group__item">
                                    <button type="button">
                                        Английский
                                        <popover></popover>
                                    </button>
                                </div>-->


                                <div class="option-block__title option-block__title_sm">
                                    Рукава
                                </div>

                                <div class="btn-group__item" v-for="(sleeve, index) in sleeves.types"
                                     :key="sleeve.text + index">
                                    <button type="button" :class="{ active: sleeve === sleeves.currentType}"
                                            @click="sleeves.currentType = sleeve" :disabled="sleeve.isDisabled">
                                        {{ sleeve.text }}

                                        <popover>
                                            <template v-if="sleeve.hasPopover">
                                                <div class="product-slider__img"><img
                                                        src="./img/popover-img.png"/></div>
                                                <div class="product-slider__img"><img
                                                        src="./img/upper-part.png"/>
                                                </div>
                                            </template>
                                        </popover>

                                    </button>
                                    <info-popover v-if="sleeve.hasInfo"></info-popover>
                                </div>

                                <div class="option-block__title option-block__title_sm">
                                    Завязки (пояс)
                                </div>

                                <div class="btn-group__item" v-for="(belt, index) in belts.types"
                                     :key="belt.text + index + index">
                                    <button type="button" :class="{ active: belt === belts.currentType}"
                                            @click="belts.currentType = belt" :disabled="belt.isDisabled">
                                        {{ belt.text }}

                                        <popover>
                                            <template v-if="belt.hasPopover">
                                                <div class="product-slider__img"><img
                                                        src="./img/popover-img.png"/></div>
                                                <div class="product-slider__img"><img
                                                        src="./img/upper-part.png"/>
                                                </div>
                                            </template>
                                        </popover>

                                    </button>
                                    <info-popover v-if="belt.hasInfo"></info-popover>
                                </div>


                                <div class="option-block__title option-block__title_sm">
                                    Карманы
                                </div>

                                <div class="btn-group__item" v-for="(pocket, index) in pockets.types"
                                     :key="pocket.text + index">
                                    <button type="button" :class="{ active: pocket === pockets.currentType}"
                                            @click="pockets.currentType = pocket" :disabled="pocket.isDisabled">
                                        {{ pocket.text }}

                                        <popover>
                                            <template v-if="pocket.hasPopover">
                                                <div class="product-slider__img"><img
                                                        src="./img/popover-img.png"/></div>
                                                <div class="product-slider__img"><img
                                                        src="./img/upper-part.png"/>
                                                </div>
                                            </template>
                                        </popover>

                                    </button>
                                    <info-popover v-if="pocket.hasInfo"></info-popover>
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

                            <div class="btn-group__item" v-for="(supplement, index) in supplements" :key="index">
                                <button type="button" :class="{ active: supplement.checked }"
                                        @click="supplement.checked = !supplement.checked">
                                    {{ supplement.text }}

                                    <popover>
                                        <template v-if="supplement.hasPopover">
                                            <div class="product-slider__img"><img
                                                    src="./img/popover-img.png"/></div>
                                            <div class="product-slider__img"><img src="./img/upper-part.png"/>
                                            </div>
                                        </template>
                                    </popover>
                                </button>
                            </div>

                            <!--<div class="btn-group__item">
                                <button type="button">
                                    Поясок
                                    <popover>

                                        <div class="product-slider__img"><img
                                                src="./img/popover-img.png"/></div>
                                        <div class="product-slider__img"><img src="./img/upper-part.png"/>
                                        </div>

                                    </popover>
                                </button>
                            </div>


                            <div class="btn-group__item">
                                <button type="button">
                                    Молния для кормления
                                    <popover></popover>
                                </button>
                            </div>

                            <div class="btn-group__item">
                                <button type="button">
                                    Шопер
                                    <popover>
                                        <div class="product-slider__img"><img
                                                src="./img/popover-img.png"/></div>
                                        <div class="product-slider__img"><img src="./img/upper-part.png"/>
                                        </div>
                                    </popover>
                                </button>
                            </div>


                            <div class="btn-group__item">
                                <button type="button">
                                    Кармашек с вышивкой
                                    <popover></popover>
                                </button>
                            </div>

                            <div class="btn-group__item">
                                <button type="button">
                                    Кардиган
                                    <popover>
                                        <div class="product-slider__img"><img
                                                src="./img/popover-img.png"/></div>
                                        <div class="product-slider__img"><img src="./img/upper-part.png"/>
                                        </div>
                                    </popover>
                                </button>
                            </div>


                            <div class="btn-group__item">
                                <button type="button">
                                    Резинки для волос
                                    <popover></popover>
                                </button>
                            </div>

                            <div class="btn-group__item">
                                <button type="button">
                                    Нижняя юбка
                                    <popover>
                                        <div class="product-slider__img"><img
                                                src="./img/popover-img.png"/></div>
                                        <div class="product-slider__img"><img src="./img/upper-part.png"/>
                                        </div>
                                    </popover>
                                </button>
                            </div>-->


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
                                            <li class="result-list__item">–</li>
                                            <li class="result-list__item unselected">Выберите размер</li>
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
                            Цена платья: 5 000 руб. + 500 руб. <span>за допошив</span>
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
                                Цена всех дополнений: 900 руб.
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
                measures: {
                    waist: '',
                    shoulder: '',
                    "chest-girth": '',
                    "waist-girth": '',
                    "hip-girth": '',
                    "hand-girth": '',
                },
                printType: {
                    types: ['Без принта', 'До пояса', 'Полностью'],
                    currentType: ''
                },
                sizeType: {
                    types: ['Взрослое', 'Детское'],
                    currentType: ''
                },
                euroSize: {
                    size: ['xs', 's', 'm', 'l', 'xl'],
                    currentSize: ''
                },
                bodyHeight: {
                    height: [150, 160, 170, 180, 190],
                    currentHeigt: 0,
                },
                colorsPalette: {
                    colors: ['#543c31', '#8A2220', '#A2522F', '#C4867B', '#C38120', '#365130', '#004C4B', '#154F90', '#5989B9', '#F3F4F5', '#C8C7C0', '#353228'],
                    currentColor: '',
                    currentUpColor: '',
                    currentSkirtColor: ''
                },
                styles: {
                    dressFachion: {
                        types: [
                            {src: 'straight', text: 'Прямое'},
                            {src: 'trapezoid', text: 'Трапеция'},
                            {src: 'cutting', text: 'Отрезное'},
                        ],
                        currentType: ''
                    },
                    patterns: {
                        type: ['birds', 'deer', 'fox', 'horse', 'leaves', 'leaves-2', 'pattern', 'ship', 'whales'],
                        currentType: ''
                    }
                },
                supplements: [
                    {text: 'Декоративный кармашек', hasPopover: false, checked: false},
                    {text: 'Поясок', hasPopover: false, checked: false},
                    {text: 'Молния для кормления', hasPopover: false, checked: false},
                    {text: 'Шопер', hasPopover: false, checked: false},
                    {text: 'Кармашек с вышивкой', hasPopover: false, checked: false},
                    {text: 'Кардиган', hasPopover: true, checked: false},
                    {text: 'Резинки для волос', hasPopover: false, checked: false},
                    {text: 'Нижняя юбка', hasPopover: false, checked: false}
                ],
                dressButtons: {
                    types: [
                        {text: 'На груди', hasPopover: true, hasInfo: false, isDisabled: false},
                        {text: 'На спине', hasPopover: false, hasInfo: false, isDisabled: false},
                        {text: '3/4', hasPopover: true, hasInfo: false, isDisabled: false},
                        {text: 'До талии', hasPopover: false, hasInfo: false, isDisabled: false},
                        {text: 'Всю длину', hasPopover: false, hasInfo: true, isDisabled: true}
                    ],
                    currentType: ''
                },
                collar: {
                    types: [
                        {text: 'Стойка', hasPopover: true, hasInfo: false, isDisabled: false},
                        {text: 'Английский', hasPopover: false, hasInfo: false, isDisabled: false}
                    ],
                    currentType: ''
                },
                sleeves: {
                    types: [
                        {text: '3/4', hasPopover: true, hasInfo: false, isDisabled: false},
                        {text: 'Стандартные', hasPopover: false, hasInfo: false, isDisabled: false}
                    ],
                    currentType: ''
                },
                belts: {
                    types: [
                        {text: 'В боковых швах', hasPopover: true, hasInfo: false, isDisabled: false},
                    ],
                    currentType: ''
                },
                pockets: {
                    types: [
                        {text: 'В боковых швах', hasPopover: true, hasInfo: false, isDisabled: false},
                    ],
                    currentType: ''
                }

            }
        },
        methods: {
            resetMeasures() {
                Object.keys(this.measures).forEach(key => this.measures[key] = "");
            },
            getImgUrl(pet) {
                var images = require.context('./img/', false, /\.svg/);
                return images('./' + pet + ".svg")
            }
        }
    }


</script>
<style lang="scss">
    @import "./assets/styles/main";
</style>
