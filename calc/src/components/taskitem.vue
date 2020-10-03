<template>
  <div class="tasks-item">
      <div class="blocks">
          <div class="block-1">
              <strong>To do:</strong> {{ task.cont }}
              {{this.name}}
          </div>
          <div class="block-2">
              Plan: {{ task.desc}}
              steps:
              {{ steps }}

          </div>
          <div class="block-3">
            <form class="create-step" @submit.prevent="newst">
            <label for="newstep">add step </label>
            <input type="text" id="newstep" name="newstep" v-model="nextstep">
            <button>
                add
            </button>
            </form>

          </div>
      </div>

  </div>
</template>

<script>
export default {
    
    name: "ti",
    props: {
    task: {
        type: Object,
        required: true

    }
    },
    data(){
        return{
            nextstep: "hi",
            steps: []
        }
    },
  methods: {
    newst() {
      if (this.nextstep){
          this.steps.push(this.nextstep)
          
          
          
          this.nextstep=""
          
          
      }
    }
  }

}
</script>

<style>

</style>