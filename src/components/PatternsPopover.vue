<template>
    <popper trigger="clickToToggle"
            @show="show"
            :options="{
                  placement: 'top',
                  modifiers: {
                        name: 'offset',
                      options: {
                        offset: ['10px', '80px'],
                      }
                  }
                }" class="popover  patterns-popover" @hide="hide">

        <div class="popper" ref="popper-js">
            <div class="popover__header">
                <div class="option-block__title">
                    Принты
                </div>

                <div class="popover__close"  @click="close">
                    Закрыть
                    <div class="popover__close-icon">
                        <img src="../img/icons/close.svg" alt="close-icon">
                    </div>
                </div>
            </div>

            <div class="popover__content">
                <div class="product-style  product-style_patterns">
                    <div class="product-style__item" v-for="(pattern, index) in patterns.type"
                         :key="pattern + index">
                        <button class="product-style__btn"
                                :class="{ active: pattern === patterns.currentType }"
                                @click="patterns.currentType = pattern">
                            <img class="product-style__icon" :src="getImgUrl(pattern)"
                            >
                        </button>
                    </div>
                </div>
            </div>

        </div>

        <div class="product-style__btn product-style__link" slot="reference" >
            <a href="#" @click.prevent>еще <span>+10</span></a>
        </div>

    </popper>
</template>

<script>
    import Popper from 'vue-popperjs';


    export default {
        name: "PatternsPopover",
        components: {
            'popper': Popper
        },
        props: {
            patterns: Object
        },
        data() {
            return {
                openedPopper: null,
                activePopper: false
            }
        },
        methods: {
            close() {
                if(this.openedPopper) {
                    this.openedPopper.doClose();
                    this.activePopper = false;
                }
            },
            show(event) {
                this.openedPopper = event;
                this.activePopper = true;
            },
            hide() {
                this.activePopper = false;
            },
            getImgUrl(pet) {
                var images = require.context('../img/', false, /\.svg/);
                return images('./' + pet + ".svg")
            }
        }

    }


</script>

<style lang="scss">
</style>