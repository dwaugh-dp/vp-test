<template>
    <footer class="bg-white ">
        <div class="max-w-7xl mx-auto py-8 px-4 sm:px-6 lg:px-8 flex flex-wrap">
            <div class="w-full lg:w-1/3 mb-8 lg:mb-0">
                <h2 class="text-lg font-semibold mb-4">Social Media</h2>
                <!-- <div class="flex items-center space-x-4">
                    <a href="#">
                        <img src="path/to/facebook-icon.svg" alt="Facebook" class="h-6 w-6" />
                    </a>
                    <a href="#">
                        <img src="path/to/twitter-icon.svg" alt="Twitter" class="h-6 w-6" />
                    </a>
                    <a href="#">
                        <img src="path/to/instagram-icon.svg" alt="Instagram" class="h-6 w-6" />
                    </a>
                    <a href="#">
                        <img src="path/to/linkedin-icon.svg" alt="LinkedIn" class="h-6 w-6" />
                    </a>
                </div> -->
            </div>
            <div class="w-full lg:w-1/3 mb-8 lg:mb-0">
                <h2 class="text-lg font-semibold mb-4">Links</h2>
                <ul class="text-sm mb-2 ">
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About Us</a></li>
                    <li><a href="#">Pricing</a></li>
                    <li><a href="#">FAQ</a></li>
                </ul>
            </div>
            <div class="w-full lg:w-1/3 mb-8 lg:mb-0">
                <h2 class="text-lg font-semibold mb-4">Contact Us</h2>
                <p class="flex items-center text-sm mb-2"><img src="~/assets/images/location.png" alt="Location"
                        class="h-4 w-4 mr-2" />14 Canberra Crescent,<br>Kingston 6<br>Jamaica W.I.</p>
                <p class="flex items-center text-sm mb-2"><img src="~/assets/images/phone.png" alt="Phone"
                        class="h-4 w-4 mr-2" />Phone: +1876-123-4567</p>
                <p class="flex items-center text-sm"><img src="~/assets/images/mail.png" alt="Email"
                        class="h-4 w-4 mr-2" />Email: info@venuepro.io</p>
            </div>
        </div>
        <div class="bg-gray-100 text-center py-4">
            <p class="text-sm">&copy; 2023 VenuePro. All rights reserved.</p>
        </div>
    </footer>
</template>
  
  
<script>
export default {
    name: 'Footer'
}
</script>
  
<style scoped>
a {
    /* color: #fff; */
    text-decoration: none;
    transition: all 0.3s ease-in-out;
}

a:hover {
    text-decoration: underline;
}
</style>
  

  