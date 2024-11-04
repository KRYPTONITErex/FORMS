<template>
  <p>Sign Up Form</p>

  <form @submit.prevent="submit">
    <p>Hi this is updated?</p>
    <label for="">Email</label>
    <input type="email" required v-model="email">
    <label for="">password</label>
    <input type="password" required v-model="password" >
    <p class="errmsg" v-if="errorMsg">{{ errorMsg }}</p>

    <label for="">User Role</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>

    <div>
      <label for="">Skills</label>
      <input type="text" @keyup="addSkill" v-model="skill">
    </div>
    <div v-for="skill in skills" :key="skill" class="skill-item">
    <p>{{ skill }}</p><span class="cross" @click="deleteSkill(skill)"><p>&#x2716;</p></span>
    </div>

    <div>
      <input type="checkbox" v-model="accept">
      <label for="">Accept terms and conditions</label>
    </div>
    <br>
      <label for="">Check Names</label><br>
    <div>
      <input type="checkbox" value="LP" v-model="names">
      <label for="">Lwin Phyo</label><br>
    </div>
    <div>
      <input type="checkbox" value="SSS" v-model="names">
      <label for="">Soe Seeseim</label><br>
    </div>
    <div>
      <input type="checkbox" value="WS" v-model="names">
      <label for="">Warain Soe</label><br>
    </div>

    <div class="align"><button class="create">Create Account</button></div>

  </form>
  <p>Email - {{ email }}</p>
  <p>Password - {{ password }}</p>
  <p>Role - {{ role }}</p>
  <p>Accept - {{ accept }}</p>
  <p>names - {{ names }}</p>

</template>


<script>
export default {
  data(){
    return{
      email:"LWINPHYO@GMAIL.COM",
      password:"",
      role:"designer",
      accept:true,
      names:[],
      skills:[],
      skill:"",
      errorMsg:""
    }
  },
  methods: {
    addSkill(e){
      if(e.key==="," && this.skill){
        this.skills.push(this.skill);
        this.skill=""
      }
    },
    deleteSkill(skill){
      this.skills=this.skills.filter(loopskill=>{
        // console.log(skill);
        return loopskill!=skill;
      })
    },
    submit(){
    // console.log("sunmitted")
      if(this.password.length<8){
        this.errorMsg="PASSWORD must be at least 8 characters"
      }
    }
  }

}
</script>

<style>

    form{
        max-width: 400px;
        margin: 30px auto;
        background: rgb(253, 253, 252);
        text-align: left;
        padding: 40px;
        border-radius: 10px;
    }
    label{
        color: #451f1f;
        display: inline-block;
        margin: 20px 0 15px;
        font-size: 0.6em;
        text-transform: uppercase;
        letter-spacing: 1px;
        font-weight: bold;
    }
    input{
        display: block;
        padding: 10px 6px;
        width: 100%;
        box-sizing: border-box;
        border: none;
        border-bottom: 1px solid #7d6767;
        color: #555;
    }
    input[type="checkbox"]{
      display: inline-block;
      width: 16px;
      margin: 0 8px 0 0;
      position: relative;
      top: 2px;
    }
    .skill-item { 
      display: flex; 
      align-items: center; 
      gap: 8px; 
    }
    .cross { 
      cursor: pointer; 
      color: red; 
    }
    .create{
      background-color: royalblue;
      padding: 8px;
      color: white;
      border-radius: 10px;
      border: 1px rgba(251, 251, 66, 0.821) solid;
      box-shadow: #555 3px 3px 3px;
    }
    .align{
      text-align: center;
    }
    .errmsg{
      background-color: crimson;
      color: rgb(255, 253, 253);
      border-radius: 5px;
      text-align: center;
    }

</style>