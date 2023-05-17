<template>
    <div class="flex h-screen py-16 px-56 background50">
        <div class="w-2/3 ">
            <div class="w-full h-full ">
                <div class="h-full  bg-white  cshadow border-2 border-transparent">
                    <!-- <div class=" w-full h-4/5   "> -->
                    <!-- Content for the left inner container goes here -->
                    <div class="px-12 py-16">
                        <div>
                            <input type="range" min="5" max="20" step="5" list="sliderValues" v-model="sliderValue"
                                class="bg-blue-400">
                            <datalist id="sliderValues">
                                <option value="0"></option>
                                <option value="5">5</option>
                                <option value="10">10</option>
                                <option value="20">20</option>
                            </datalist>
                            <p>Up to {{ sliderValue }} rooms </p>
                        </div>
                    </div>

                    <div class="flex items-center my-8 mx-4 ">
                        <!-- </div> -->
                        <ul class="mt-6 mb-6 mx-8">
                            <li class="flex items-center mb-2 ">&#x2022;
                            Accept Bookings online
                        </li>
                        <li class="flex items-center mb-2 ">&#x2022;
                            Unlimited Appointments
                        </li>
                        <li class="flex items-center mb-2">&#x2022;
                            Customizable Booking Page
                        </li>
                        </ul>

                        <!-- <BaseToggle/> -->
                    </div>
                </div>
            </div>
        </div>


        <div class="w-1/3 bg-white ">
            <div
                class="w-full h-4/5 bg-gradient-to-b from-blue-500 to-blue-900   flex-col items-center justify-center cshadow">
                <!-- Content for the right inner container goes here -->
                <div class="text-white font-semibold text-lg items-center justify-center py-4 px-16" id="ptype">VENUEPRO SPACES</div>
                <div class="text-white font-bold text-7xl px-24" id="p">${{ sliderValue }}</div>
                <div class="text-white font-semibold text-lg items-center justify-center px-28" id="interval">/month</div>

                <p class="text-white text-sm m-4" id="pinfo">Manage your space with  trusted groups</p>

               <a href="https://dashboard.stripe.com/register"
                    class="uppercase my-4 mx-20 link-arrow bg-blue-500 hover:bg-blue-700 text-white text-sm font-semibold py-1 px-2 rounded-full mt-6 transition-all duration-200 ease-in-out">Sign
                    Up</a>
            </div>
        </div>

    </div>
</template>
  
<script>
export default {
    data() {
        return {
            sliderValue: 5,
        }
    },
};
</script>
  
<style>
@import url('https://fonts.cdnfonts.com/css/gt-walsheim-pro');

.cshadow {
    box-shadow: 6px 6px 24px 0 rgba(52, 51, 62, .1);
}



.background50 {
    background: linear-gradient(to bottom,
            rgba(147, 197 ,253, 0.15) 0%,
            rgba(147, 196, 253, 0.15) 50%,
            white 50%,
            white 100%);
}

.cfont {
    font-family: 'GT Walsheim Pro', sans-serif;
}
</style>
  