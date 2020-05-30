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

        <span class="btn-group__item_preview" slot="reference" >
            <img src="../img/icons/eye.svg" alt="icon-eye" v-if="!this.activePopper">
            <img src="../img/icons/active-eye-icon.svg" alt="icon-eye" v-else="this.activePopper">
        </span>
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
            patterns: {
                type: Object,
                validator: function (value) {
                    return value !== null
                }
            }
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