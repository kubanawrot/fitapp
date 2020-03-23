<template>
  <div
    class="home flex flex-col sm:flex-col md:flex-col lg:flex-col xl:flex-row sm:justify-center md:justify-center lg:justify-around xl:justify-around"
  >
    <div
      class="mx-auto my-16 w-11/12 xl:w-1/4 lg:w-4/5 sm:w-4/5 md:w-4/5"
      v-for="training in trainings"
      :key="training.id"
    >
      <div class="flex mb-6 font-semibold">
        <!-- <font-awesome-icon class="mr-2 pt-1 text-xl" icon="dumbbell" /> -->
        <div class="w-2 ml-2 mr-4 rounded-sm bg-teal-800"></div>
        <span>{{ training.title }}</span>
      </div>
      <div
        class="flex flex-row flex-wrap justify-around max-w-full m-2 p-4 rounded-md bg-gray-100 shadow-sm"
      >
        <div v-for="(exercise, index) in training.exercises" :key="index" class="flex-grow m-5">
          <div
            class="w-24 p-1 pl-2 rounded-lg bg-teal-800 text-gray-200 shadow font-medium"
          >{{ exercise.exercise }}</div>
          <div class="h-22 mt-4 mb-2 p-2 rounded-lg border-solid bg-gray-300 shadow-md">
            <div class="flex flex-row justify-between items-center mb-2">
              <span class="font-medium">runs:</span>
              <div class="flex flex-row">
                <button
                  @click="exercise.runs = exercise.runs - 1"
                  class="bg-gray-500 hover:bg-gray-800 text-white font-bold py-2 px-4 rounded-l"
                >-</button>
                <div class="w-12 bg-white text-center leading-9">
                  {{
                  exercise.runs
                  }}
                </div>
                <button
                  @click="exercise.runs = exercise.runs + 1"
                  class="bg-gray-700 hover:bg-gray-800 text-white font-bold py-2 px-4 rounded-r"
                >+</button>
              </div>
            </div>
            <div class="flex flex-row justify-between items-center mb-2">
              <span class="font-medium mr-4">repeats:</span>
              <div class="flex flex-row">
                <button
                  @click="exercise.repeats = exercise.repeats - 1"
                  class="bg-gray-500 hover:bg-gray-800 text-white font-bold py-2 px-4 rounded-l"
                >-</button>
                <div class="w-12 bg-white text-center leading-9">
                  {{
                  exercise.repeats
                  }}
                </div>
                <button
                  @click="exercise.repeats = exercise.repeats + 1"
                  class="bg-gray-700 hover:bg-gray-800 text-white font-bold py-2 px-4 rounded-r"
                >+</button>
              </div>
            </div>
            <div class="flex flex-row justify-between items-center">
              <span class="font-medium">load:</span>
              <div class="flex flex-row">
                <button
                  @click="exercise.load = exercise.load - 1.25"
                  class="bg-gray-500 hover:bg-gray-800 text-white font-bold py-2 px-4 rounded-l"
                >-</button>
                <div class="w-12 bg-white text-center leading-9">
                  {{
                  exercise.load
                  }}
                </div>
                <button
                  @click="exercise.load = exercise.load + 1.25"
                  class="bg-gray-700 hover:bg-gray-800 text-white font-bold py-2 px-4 rounded-r"
                >+</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      trainings: [
        {
          title: "Training 1",
          slug: "training-1",
          exercises: [
            { exercise: "exercise 1", runs: 4, repeats: 8, load: 50 },
            { exercise: "exercise 2", runs: 4, repeats: 8, load: 80 },
            { exercise: "exercise 3", runs: 3, repeats: 8, load: 50 },
            { exercise: "exercise 4", runs: 4, repeats: 8, load: 20 },
            { exercise: "exercise 5", runs: 4, repeats: 8, load: 50 },
            { exercise: "exercise 6", runs: 3, repeats: 8, load: 50 }
          ],
          id: 1
        },
        {
          title: "Training 2",
          slug: "training-2",
          exercises: [
            { exercise: "exercise 7", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 8", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 9", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 10", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 11", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 12", runs: 1, repeats: 8, load: 50 }
          ],
          id: 2
        },
        {
          title: "Training 3",
          slug: "training-3",
          exercises: [
            { exercise: "exercise 13", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 14", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 15", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 16", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 17", runs: 1, repeats: 8, load: 50 },
            { exercise: "exercise 18", runs: 1, repeats: 8, load: 50 }
          ],
          id: 3
        }
      ],
      increaseRuns() {
        this.exercise.runs += 1;
      }
    };
  }
};
</script>

<style>
img {
  margin: auto;
}

button:focus {
  outline: none !important;
  border: none !important;
}
</style>
