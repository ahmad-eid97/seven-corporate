<template>
    <div>
        <!-- Footer Style Seven Start -->
        <footer class="bg-faded pt-70 pb-40 bg-theme-color-2">
            <div class="container">
                <div class="section-content">
                    <div class="row">
                        <div class="col-md-3">
                            <div class="footer-item footer-widget-one">
                                <img class="footer-logo mb-25" src="/assets/images/logo2.png" alt="logoImage">
                                <p>Dolorum quae quis cumque officia labore delectus at animi ducimus non nisi, dolores
                                    sapiente</p>
                                <hr>


                            </div>
                        </div>

                        <div class="col-md-3">
                            <div class="footer-item">
                                <div class="footer-title">
                                    <h4><span>CONTACT INFO</span></h4>

                                </div>
                                <ul class="footer-list footer-contact mb-10">
                                    <li><i class="pe-7s-call"></i> Phone: 001 (407) 901-6400</li>
                                    <li><i class="pe-7s-print"></i> Fax: 001 (407) 901-6400</li>
                                    <li><i class="pe-7s-mail"></i> <a href="mailto:">Email: {{$store.state.websiteSettings.find(one => one.key === 'email').plain_value}}</a></li>
                                </ul>


                            </div>
                        </div>

                        <div class="col-md-3">
                            <div class="footer-item">
                                <div class="footer-title">
                                    <h4>Services</h4>

                                </div>
                                <ul class="footer-list">
                                    <li><a href="#">Investment & Stock Exchange (clickable)</a></li>
                                    <li><a href="#">Business Advisory</a></li>
                                    <li><a href="#">Accounting & Tax Services</a></li>
                                    <li><a href="#">Finance & Banking</a></li>
                                    <li><a href="#">International Banking</a></li>
                                    <li><a href="#">Business Consulting</a></li>
                                </ul>

                            </div>
                        </div>

                        <div class="col-md-3">
                            <div class="footer-item">
                                <div class="footer-title">
                                    <h4>RECENT NEWS</h4>

                                </div>
                                <ul class="footer-list">
                                    <!-- <li><a href="#">About Us</a></li> -->
                                    <li><b-nav-item :to="localePath('/about')">About Us</b-nav-item></li>
                                    <li><b-nav-item :to="localePath('/services')">Services</b-nav-item></li>
                                    <li><b-nav-item :to="localePath('/team')">Team</b-nav-item></li>
                                    <li><b-nav-item :to="localePath('/testimonials')">Gallery</b-nav-item></li>
                                    <li><b-nav-item :to="localePath('/blogs')">Blogs</b-nav-item></li>
                                    <li><b-nav-item :to="localePath('/contact')">Contact</b-nav-item></li>
                                </ul>

                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </footer>
        <section class="footer-copy-right bg-theme-color-2 text-white p-0">
            <div class="container">
                <div class="row">
                    <div class="col-12 text-center">
                        <p>© 2020, All Rights Reserved, Design & Developed By:<a href="#"> Rail Coder</a></p>
                    </div>
                </div>
            </div>
        </section>
        <!-- Footer Style Seven End -->
    </div>
</template>

<script>


export default {
    name: 'AppFooter',
    components: {},
    data() {
        return {
            
        }
    },
    beforeMount () {
        
    },
    methods : {
        
    }
}
</script>

<style scoped lang="scss">
.footer-list {
    li {
        color: rgb(160, 160, 160);
    }
}
</style>