<template>
  <div class = "todo-list">
    <div class="todo-list-panel">
        <h3 class="title">To do list</h3>
        <div class=todo-wrapper> 
            <taskitem v-for="(task, index) in td.tasks" :key="index" :task="task" />
            
        </div>
        <form class="create-task" @submit.prevent="newitem">
            <label for="newtask"><strong> To do: </strong></label>
            <input type="text" id="newtask" name="newtask" v-model="newtaskcont"><br>
            <label for="newplan">plan:</label>
            <textarea id="newplan" name="newplan" rows="4" v-model="newtaskdesc"/>
            <button>
                +
            </button>
        </form>
    </div>

  </div>

</template>

<script>
import taskitem from "./taskitem";

export default {
  name: 'Todo',
  components: { taskitem },
  data() {
    return{
        newtaskcont: "hi",
        newtaskdesc: "",
      followers: 0,
      td: {
        id: 1,
        username: 'username',
        firstName: 'first',
        lastName: 'last',
        email: 'e@mail.com',
        isAdmin: true,
        tasks: [
            {cont: 'wake up', desc: 'agsggjgjafgsgsdfsdfsdfs sdfasdfsdfd sdfasdf s'},
            {cont: 'wake up', desc: 'sdfmomjmkm uhu9h huh '},
            {cont: 'wake up', desc: 'dfhh dfuh uih'}
        ]


      }   
    }
  },
  watch:{
    followers(newFollowerCount, oldFollowerCount){
      if (oldFollowerCount < newFollowerCount){
        console.log('+1')
      }
    }
  },
  computed: {
    fullName() {
      return this.user.firstName + " " + this.user.lastName;
    }
  },
  methods: {
    newitem() {
      if (this.newtaskcont){
          this.td.tasks.push({
              cont: this.newtaskcont,
              desc: this.newtaskdesc,
            
          })
          this.newtaskcont="",
          this.newtaskdesc=""
      }
    }
  },
  mounted(){
    this.followUser()
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>