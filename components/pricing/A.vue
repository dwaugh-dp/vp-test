<template>
    <div class="flex h-screen py-16 px-56 background50">
        <div class="w-2/3 ">
            <div class="w-full h-full ">
                <div class="h-full  bg-white  cshadow border-2 border-transparent">
                    <!-- Content for the left inner container goes here -->
                    <div class="px-12 py-16 ">
                        <div class="flex-col items-center justify-center">
                            <BaseToggle class="my-4" @value-changed="handleSelectedValueChanged" />
                        </div>
                        <div class="flex items-center">



                            <input type="range" id="slider" name="slider" min="5" max="15" step="5" list="sliderValues"
                                v-model="sliderValue" @input="handleSliderValueChanged"
                                class="w-full bg-blue-400 h-2 rounded-full  cursor-pointer">
                            <datalist id="sliderValues">
                                <option value="5">5</option>
                                <option value="10">10</option>
                                <option value="15">15</option>
                            </datalist>
                        </div>
                        <div class="flex justify-between mt-4">
                            <span class="text-xs">5 rooms</span>
                            <span class="text-xs">10 rooms</span>
                            <span class="text-xs">15 rooms</span>
                        </div>
                        <p class="text-sm mt-4">Up to {{ sliderValue }} rooms</p>
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
                class="w-full h-4/5 bg-gradient-to-b from-blue-500 to-blue-900 text-center flex-col items-center justify-center cshadow">
                <!-- Content for the right inner container goes here -->
                <div class="text-white font-semibold text-base items-center justify-center py-4 px-16" id="ptype">VENUEPRO
                    SPACES</div>
                <div class="text-white font-bold text-6xl " id="p">{{ price }}</div>
                <div class="text-white font-semibold text-lg items-center justify-center " id="interval">/year</div>

                <p class="text-white text-base  m-4" id="pinfo">Manage your space with trusted groups</p>

                <a href="#"
                    class="uppercase my-4 mx-20 link-arrow bg-blue-500 hover:bg-blue-700 text-white text-sm font-semibold py-1 px-2 rounded-full mt-6 transition-all duration-200 ease-in-out">Sign
                    Up</a>
            </div>
        </div>

    </div>
</template>
  
<script>
import Stripe from 'stripe';
const stripe = await Stripe('sk_test_51LnPXHLaFe4PblPMUFe3Z65aBMLLcigKhITlbjGP3hzvzVbdIXoElbb4wcM0sCZLBudh0yJBL33Tx0S4xIk53F9J00zVNGCJYY', { apiVersion: '2022-11-15' })

const yearlyprices = await stripe.prices.list({ expand: ['data.product'], recurring: { interval: 'year' }, lookup_keys: ['15rooms_annual', '10rooms_annual', '5rooms_annual'] });
const monthlyprices = await stripe.prices.list({ expand: ['data.product'], recurring: { interval: 'month' }, lookup_keys: ['15rooms_monthly', '10rooms_monthly', '5rooms_monthly'] });

const limit_5 = monthlyprices.data.find(price => price.lookup_key === '5rooms_monthly');
const limit_10 = monthlyprices.data.find(price => price.lookup_key === '10rooms_monthly');
const limit_15 = monthlyprices.data.find(price => price.lookup_key === '15rooms_monthly');
const limit_5_annual = yearlyprices.data.find(price => price.lookup_key === '5rooms_annual');
const limit_10_annual = yearlyprices.data.find(price => price.lookup_key === '10rooms_annual');
const limit_15_annual = yearlyprices.data.find(price => price.lookup_key === '15rooms_annual');

const prices = {
    monthly: {
        5: limit_5.unit_amount / 100,
        10: limit_10.unit_amount / 100,
        15: limit_15.unit_amount / 100,
    },
    annual: {
        5: limit_5_annual.unit_amount / 100,
        10: limit_10_annual.unit_amount / 100,
        15: limit_15_annual.unit_amount / 100,
    }
}

//use the prices array to set the price of the slider
export default {
    data() {
        return {
            sliderValue: 5,
            isAnnual: true,
        }
    },
    computed: {
        price() {
            const monthlyPrice = prices.monthly[this.sliderValue]
            const annualPrice = prices.annual[this.sliderValue]
            return this.isAnnual ? `$${annualPrice}` : `$${monthlyPrice}`
        },

        interval() {
            return this.isAnnual ? `/year` : `/month`
        }
    },
    methods: {
        handleSelectedValueChanged() {

            this.isAnnual = !this.isAnnual
            this.updatePrice()
        },
        handleSliderValueChanged() {
            this.updatePrice()
        },
        updatePrice() {
            const p = document.getElementById('p')
            p.textContent = this.price

            const interval = document.getElementById('interval')
            interval.textContent = this.interval
        },
    },
};

// export default {

// }
</script>
  
<style>
@import url('https://fonts.cdnfonts.com/css/gt-walsheim-pro');

.cshadow {
    box-shadow: 6px 6px 24px 0 rgba(52, 51, 62, .1);
}



.background50 {
    background: linear-gradient(to bottom,
            rgba(147, 197, 253, 0.15) 0%,
            rgba(147, 196, 253, 0.15) 50%,
            white 50%,
            white 100%);
}

.cfont {
    font-family: 'GT Walsheim Pro', sans-serif;
}
</style>
  