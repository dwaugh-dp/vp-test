<template>
    <div class="w-full bg-blue-300 bg-opacity-10">
        <section class="bg-trading-tools relative max-w-full sm:mx-4 my-20 py-8  overflow-hidden">
            <div class="relative max-w-screen-xl px-4 sm:px-2 mx-auto grid grid-cols-12 gap-x-6">


                <div class="col-span-12 lg:col-span-6 sm:hidden" v-bind="$attrs">
                    <div class="w-full sm:mt-20 xl:mt-0">
                        <img src="~/assets/images/meeting.svg" class="w-full" alt="" />
                    </div>
                </div>


                <div class="col-span-12 lg:col-span-6 space-y-8 sm:space-y-6 px-8 sm:px-6 mt-8">
                    <h1 class="text-3xl pl-4 font-semibold md:text-5xl">VenuePro <span class="text-header-gradient font-bold ">Spaces</span>
                    </h1>
                    <ul class="list-disc pl-10">
                       <li>
                        <div class="space-y-2">
                        <h4 class="text-lg font-medium">Flat monthly fee for unlimited room access</h4>
                        <p class="paragraph text-sm xl:text-base">
                            Get unlimited room access for a flat monthly fee, providing cost-effective scalability and a
                            self-service portal for team leads to manage meeting bookings.

                        </p>
                    </div>
                       </li>
                          <li>
                            <div class="space-y-2">
                            <h4 class="text-lg font-medium">Room and Building Configuration</h4>
                            <p class="paragraph text-sm xl:text-base">
                             Configure rooms and buildings to fit your needs with customizable sizes, layouts, amenities,
                             labels, booking policies, and support for multiple locations.
                            </p>
                        </div>

                            </li>
                            <li>
                                <div class="space-y-2">
                                <h4 class="text-lg font-medium">Digital Signage</h4>
                                <p class="paragraph text-sm xl:text-base">
                                    Display real-time room availability, booking details, and custom branding on digital signs
                                    throughout your building for better communication and organization.
                                </p>
                            </div>
                            </li>
                            <li>
                                <div class="space-y-2">
                                <h4 class="text-lg font-medium">Comprehensive Meeting Management</h4>
                                <p class="paragraph text-sm xl:text-base">
                                    Our solution covers all aspects of meeting management, including scheduling, booking,
                                    notifications, file uploads, agendas, attendee lists, reminders, recordings, and analytics.
                                </p>
                            </div>
                            </li>
                    </ul>
                 

                    <div class="flex flex-col sm:flex-row justify-center space-y-4 sm:space-y-0 sm:space-x-4 mt-2">
          <BaseButton name="Sign Up" url="/" 
            class="max-w-full px-8 py-4 bg-gradient-to-r from-[#468ef9] to-[#0c66ee] border border-[#0c66ee] text-white" />
          <BaseOButton name="Learn More" url="/" 
            class="max-w-full px-6 py-4 bg-inherit text-gradient border border-[#0c66ee] flex items-center justify-center text-blue-700 hover:text-white" />
        </div>
                </div>
                <div class="col-span-12 lg:col-span-6 hidden sm:block" v-bind="$attrs">
                    <div class="w-full sm:mt-20 xl:mt-0">
                        <img src="~/assets/images/meeting.svg" class="w-full" alt="" />
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>
<script>
import BaseButton from "@/components/base/Button.vue";

export default {
    components: {

        BaseButton,
    },
};
</script>
<style scoped>
.text-header-gradient {
  background: rgb(57, 132, 244);
  background: linear-gradient(169.4deg, #3984f4 -6.01%, #8fd3f4 36.87%, #2f7cf0 78.04%, #0e65e8 103.77%);
  background-clip: text;
  -webkit-text-fill-color: transparent;


}
</style>