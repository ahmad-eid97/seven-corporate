<template>
    <div class="medium-bar">
            <div class="container">
                <div class="row">
                    <div class="col-lg-12">
                        <div class="d-flex bd-highlight align-items-center">
                            <div class="col-md-10">
                                <div class="ml-auto bd-highlight">
                                    <div class="account-cad">
                                        <div class="item mb-30">

                                            <div class="text">
                                                <h5>GET FREE CONSULTATION!</h5>
                                                <h6>001-234-5678</h6>
                                            </div>
                                        </div>

                                    </div>
                                </div>
                            </div>
                            <div class="col-md-2">
                                <div class="bd-highlight">
                                    <div class="logo-box">
                                        <a href="/"><img src="/assets/images/logo.png" alt="logoImage"
                                                style="width: 250px;"></a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
export default {
    name: 'AppMidBar',
    components: {
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
.medium-bar {
    @include md {
        display: none;
    }
}
</style>