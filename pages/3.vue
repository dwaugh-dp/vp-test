<template>
    <div class="flex h-screen w-screen">
        <div class="relative w-full h-full">
            <div class="absolute inset-0 bg-cover min-h-screen min-w-fit bg-no-repeat bg-blend-multiply grayscale bg-gray-400 bg-opacity-95"
                style="background-image: url('https://iili.io/HUCfHEx.jpg')"></div>
            <div class="flex flex-col justify-center items-center w-full h-full">
                <div class="grayscale-0">
                    <div class="w-screen h-screen flex">
                        <div class="w-1/2 h-full text-white bg-white bg-opacity-10">
                           <div class="absolute bottom-0 px-6">
                            <h1 class="text-6xl mb-2 italic"> Board Room 1 </h1>
                            <h1 id="date-display" class=" text-9xl font-extrabold italic text-white mb-5 ">
                                {{ today }}
                            </h1>
                           </div> 
                        </div>

                        <div class="w-1/2 h-full bg-white bg-opacity-10 flex-col overflow-y-auto px-16 py-4">
                            <DisplayTile v-for="tile in tiles" :key="tile.id" :group="tile.group"
                                :meeting_name="tile.meeting_name" :meeting_duration="tile.meeting_duration"
                                :meeting_date="tile.meeting_date" />
                            <h1 class="text-black">bob</h1>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
import DisplayTile from "@/components/display/tile.vue";
import moment from "moment";

export default {
    components: {
        DisplayTile,
    },
    data() {
        return {
            today: "3:00 PM",
            tiles: [
                {
                    id: 1,
                    group: "ACME",
                    meeting_name: "Monthly Meeting",
                    meeting_duration: "9am-11am",
                    meeting_date: "2023-05-10",
                },
                {
                    id: 2,
                    group: "ACME",
                    meeting_name: "Monthly Meeting",
                    meeting_duration: "9am-11am",
                    meeting_date: "2023-12-10",
                },
                {
                    id: 3,
                    group: "ACME",
                    meeting_name: "Monthly Meeting",
                    meeting_duration: "9am-11am",
                    meeting_date: "2023-12-10",
                },

                {
                    id: 4,
                    group: "ACME",
                    meeting_name: "Monthly Meeting",
                    meeting_duration: "9am-11am",
                    meeting_date: "2023-12-10",
                },
                {
                    id: 5,
                    group: "ACME",
                    meeting_name: "Monthly Meeting",
                    meeting_duration: "9am-11am",
                    meeting_date: "2023-12-10",
                },
                {
                    id: 6,
                    group: "ACME",
                    meeting_name: "Monthly Meeting",
                    meeting_duration: "9am-11am",
                    meeting_date: "2023-12-10",
                },


            ],
        };
    },
};
</script>
  