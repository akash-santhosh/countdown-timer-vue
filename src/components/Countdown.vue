<template>
  <div class="radial-progress-bar">
    <vue-countdown :time="time" v-slot="{ days, hours, minutes, seconds }">
      <div class="flex-view">
        <div>
          <radial-progress-bar
            :diameter="diameter"
            :completed-steps="days"
            :total-steps="60"
            :animateSpeed="1000"
            :strokeWidth="strokeWidth"
            :innerStrokeWidth="innerStrokeWidth"
            :startColor="startColor"
            :stopColor="stopColor"
            :innerStrokeColor="innerStrokeColor"
          >
            <p class="completedSteps">{{ days }}</p>
          </radial-progress-bar>
          <span class="label-style">Days</span>
        </div>
        &nbsp;&nbsp;
        <div>
          <radial-progress-bar
            :diameter="diameter"
            :completed-steps="hours"
            :total-steps="60"
            :animateSpeed="1000"
            :strokeWidth="strokeWidth"
            :innerStrokeWidth="innerStrokeWidth"
            :startColor="startColor"
            :stopColor="stopColor"
            :innerStrokeColor="innerStrokeColor"
          >
            <p class="completedSteps">{{ hours }}</p>
          </radial-progress-bar>
          <span class="label-style">Hours</span>
        </div>
        &nbsp;&nbsp;
        <div>
          <radial-progress-bar
            :diameter="diameter"
            :completed-steps="minutes"
            :total-steps="60"
            :animateSpeed="1000"
            :strokeWidth="strokeWidth"
            :innerStrokeWidth="innerStrokeWidth"
            :startColor="startColor"
            :stopColor="stopColor"
            :innerStrokeColor="innerStrokeColor"
          >
            <p class="completedSteps">{{ minutes }}</p>
          </radial-progress-bar>
          <span class="label-style">Minutes</span>
        </div>
        &nbsp;&nbsp;
        <div>
          <radial-progress-bar
            :diameter="diameter"
            :completed-steps="seconds"
            :total-steps="60"
            :animateSpeed="1000"
            :strokeWidth="strokeWidth"
            :innerStrokeWidth="innerStrokeWidth"
            :startColor="startColor"
            :stopColor="stopColor"
            :innerStrokeColor="innerStrokeColor"
          >
            <p class="completedSteps">{{ seconds }}</p>
          </radial-progress-bar>
          <span class="label-style">Seconds</span>
        </div>
      </div>
    </vue-countdown>
  </div>
</template>

<script>
import RadialProgressBar from "vue-radial-progress";
import VueCountdown from "@chenfengyuan/vue-countdown";

export default {
  name: "CountdownTimerComponent",
  data() {
    const now = new Date();
    const deadline = new Date("September 24 2023 23:59:59");
    return {
      diameter: 95,
      strokeWidth: 6,
      innerStrokeWidth: 3,
      time: deadline - now,
      startColor: "#07e7f7",
      stopColor: "#3d377e",
      innerStrokeColor: "#E5E5E5",
    };
  },
  components: {
    RadialProgressBar,
    VueCountdown,
  },
};
</script>
<style scoped>
.flex-view {
  display: flex;
}
.completedSteps {
  font-size: 35px;
  color: #E5E5E5;
}
.label-style {
  color: #e9e9e9;
  font-size: 15px;
}
</style>
