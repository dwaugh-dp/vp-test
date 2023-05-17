<template>
    <div class="flex h-screen py-16 px-56 background50">
        <div class="w-2/3 ">
            <div class="w-full h-full ">
                <div class="h-full  bg-white  cshadow border-2 border-transparent">
                    <!-- <div class=" w-full h-4/5   "> -->
                    <!-- Content for the left inner container goes here -->
                    <div class="flex items-center my-8 mx-4 ">
                        <!-- </div> -->
                        <ul class="mt-6 mb-6 mx-8">
                            <li class="flex items-center cfont">
                                <input type="checkbox" checked id="toggle" class=""><label for="toggle"
                                    class=" text-gray-600 text-lg font-light ">&nbsp;Stripe
                                    Integration
                                </label>
                            </li>

                            <li class="flex items-center cfont">
                                <p class=" text-gray-600  text-lg font-light ">&#x2022; &nbsp; Accept Bookings
                                    online</p>
                            </li>
                            <li class="flex items-center cfont">
                                <p class=" text-gray-600  text-lg font-light ">&#x2022; &nbsp; Unlimited
                                    Appointments</p>
                            </li>
                            <li class="flex items-center cfont">
                                <p class=" text-gray-600  text-lg font-light ">&#x2022; &nbsp; Customizable
                                    Booking Page</p>
                            </li>
                            <li class="flex items-center cfont">
                                <p class=" text-gray-600  text-lg font-light ">&#x2022; &nbsp; Accept Bookings
                                    online</p>
                            </li>
                            <li class="flex items-center cfont">
                                <p class=" text-gray-600  text-lg font-light ">&#x2022; &nbsp;Unlimited
                                    Appointments</p>
                            </li>
                            <li class="flex items-center cfont">
                                <p class=" text-gray-600  text-lg font-light ">&#x2022; &nbsp; Customizable
                                    Booking Page</p>
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
                <div class="text-white font-semibold text-md items-center justify-center py-4 px-[25%]" id="ptype">REVENUE
                    SPLIT</div>
                <div class="text-white font-bold text-6xl px-[25%]" id="p">15%</div>
                <div class="text-white font-semibold text-lg items-center justify-center px-20" id="interval"></div>

                <p class="text-white text-sm m-8" id="pinfo">No monthly fees. Accept online payments with 15% revenue split
                    using Stripe Connect</p>

                <a href="https://dashboard.stripe.com/register"
                    class="uppercase my-4 mx-20 link-arrow bg-blue-500 hover:bg-blue-700 text-white text-sm font-semibold py-1 px-2 rounded-full mt-6 transition-all duration-200 ease-in-out">Sign
                    Up</a>
            </div>
        </div>

    </div>
</template>
  
<script>
export default {
    mounted() {
        const toggle = document.getElementById('toggle')
        toggle.addEventListener('change', () => {
            const price = document.getElementById('p');
            const priceDes = document.getElementById('ptype');
            const info = document.getElementById('pinfo');
            const interval = document.getElementById('interval');


            if (price) {
                if (toggle.checked) {
                    price.innerHTML = `15%`;
                    priceDes.innerHTML = `REVENUE SPLIT`;
                    info.innerHTML = `No monthly fees. Accept online payments with 15% revenue split using Stripe Connect`;
                    interval.innerHTML = ``;
                } else {
                    price.innerHTML = `$5`;
                    interval.innerHTML = `/month/service`;
                    priceDes.innerHTML = `INVOICING PLAN`;
                    priceDes.classList.replace('text-lg', 'text-md');
                    info.classList.replace('m-8', 'm-4');
                    // add an async function to fetch the price from the backend

                    info.innerHTML = `Auto generate and send invoices to your clients. No online payment option.`;
                }
            }
        })
    }
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
  