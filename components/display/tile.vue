<template>
    <div id="meeting-card" :class="cardColor + ' text-white px-4 py-4 mb-4'">
        <span>
            <h1 class=" text-lg font-medium">
                {{ group }}
            </h1>
            <h1 class=" text-xl font-bold">
                {{ meeting_name }}
            </h1>
            <h1 class=" text-lg font-medium">
                {{ meeting_duration }} &nbsp; {{ meeting_date }}
            </h1>
        </span>

    </div>
</template>

<script>

export default {
    props: {
        group: {
            type: String,
            required: true,
        },

        meeting_name: {
            type: String,
            required: true,
        },

        meeting_duration: {
            type: String,
            required: true,
        },

        meeting_date: {
            type: String,
            required: true,
        },
    },

    computed: {
        meeting_status() {
            let meeting_time = new Date(this.meeting_date);
            let current_time = new Date();
            let time_difference = meeting_time - current_time;
            let time_difference_in_minutes = time_difference / 60000;

            if (time_difference_in_minutes < 0) {
                return "Ongoing";
            } else if (time_difference_in_minutes < 60) {
                return "Within the hour";
            } else {
                return "Upcoming";
            }
        },

        cardColor() {
            if (this.meeting_status == "Ongoing") {
                return "bg-red-600";
            } else if (this.meeting_status == "Within the hour") {
                return "bg-yellow-400";
            } else {
                return "bg-blue-500";
            }
        },
    },
}
</script>


  