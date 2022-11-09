<template>
    <div class="top-bar">
        <div class="container">
            <div class="row m-0">
                <div class="col-lg-12">
                    <div class="d-flex justify-content-between align-items-center">
                        <div class="col-auto">
                            <div class="float-right">
                                <ul class="social-icon  bordered-theme">
                                    <li><a href="#">
                                        <font-awesome-icon icon="fa-brands fa-facebook-f" />
                                        </a></li>
                                    <li><a href="#"><font-awesome-icon icon="fa-brands fa-twitter" /></a></li>
                                    <li><a href="#"><font-awesome-icon icon="fa-brands fa-linkedin-in" /></a></li>
                                    <li><a href="#"><font-awesome-icon icon="fa-solid fa-wifi" /></a></li>
                                    <li><a href="#"><font-awesome-icon icon="fa-brands fa-youtube" /></a></li>
                                </ul>
                            </div>
                        </div>
                        <div class="col-auto">
                            <div class="d-flex" style="gap: 25px">
                                <div class="float-left">
                                    <p class="p-content">Welcome to e-shop!</p>
                                </div>
                                <lang-switch></lang-switch>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
import LangSwitch from '../langSwitch/langSwitch.vue'
export default {
    name: 'AppTopBar',
    components: {
        LangSwitch
    },
    data() {
        return {

        }
    },
    mounted() {
    },
    methods: {

    }
}
</script>
<style scoped lang="scss">
.top-bar {
    height: 55px;
    .social-icon {
        li {
            svg {
                max-width: 20px;
            }
        }
    }
}
</style>