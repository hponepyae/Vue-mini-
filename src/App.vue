
<template>
  <div class="">
    <h1 class=" bg-blue-600 text-white text-center p-3" >ToDO</h1>
    <div class="my-5 flex justify-end align-items-end">
      <div class=" mr-3">
        <input type="text" class='border border-slate-800 mr-3 p-3 outline-0' placeholder="add task" v-model="putData" v-on:keyup.enter="dataAdd()">
         <button class=" btn btn-danger" @click="dataAdd()">click</button>
      </div>
    </div>
    <div class="w-5/6 mx-auto mt-10">
      <div class=" grid grid-cols-2 mb-5  ">
        <div class=" text-center" >Task</div>
        <div class=" text-center">Done</div>
      </div>
            <div class=" w-4/4  my-4 text-center" v-if="task == ''">There is no task</div>
       <div class=" grid grid-cols-2" v-for=" (tasks,index) in miko" :key="index">
          
           
             <div class=" text-center" :class="tasks.done ? 'delete-text' : ''">{{ tasks.action }}</div>
              <div class=" text-center" >
                <input type="checkbox" v-model="tasks.done" >
              </div>
         
        </div>

        <div class="bg-red-600 text-white mt-5 flex justify-center align-items-center">
          <h3 class="mr-2">Hide Content</h3>
          <input  type="checkbox" v-model="check">
        </div>
    </div>

    

    <div class="" @mouseover="like()" v-if="!lokii">meko</div>
    <div class=" text-danger" v-if="lokii" @mouseleave="like()" >love</div>

    <!-- pritic
    <div class=" w-4/4 bg-warning my-11 relative ">
       <div class=" flex justify-end mr-8" @click="chue()">
        menu
       </div>
       <ul class=" w-1/6 bg-success p-3 text-center absolute right-1 top-7" v-if="menu" @mouseleave="chue()">
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
       </ul>
    </div>

    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolorum veritatis quidem voluptates voluptate voluptatem accusamus eveniet laudantium fugit eos expedita voluptatum, saepe adipisci voluptatibus doloremque quos deserunt quaerat perferendis ad!</p>
     -->
  </div>
</template>


<script>
export default {
  name: 'App',
  data: () => ({
    name: "mgmg",
    check: false,
    putData: '',
    task: [],
    umber: "babe",
    menu: false,
    lokii:false,
  }),
  computed: {
    miko() {
      return this.check ? this.task.filter((v)=> v.done != true) : this.task;
    }
  },
  methods: {
    dataAdd() {
      this.task.push({
        action: this.putData,
        done: false
      })
      this.putData = ''
    },

    like() {
     this.lokii=this.lokii?false:true
    },

    chue() {
      this.menu=this.menu?false:true
    }

    
   
  }
}
</script>

<style>
.delete-text {
  text-decoration: line-through;
}
</style>




