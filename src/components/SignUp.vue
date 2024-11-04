<template>
  <p>Sign Up Form</p>

  <form>
    <p>Hi this is updated?</p>
    <p>why nochanges</p>
    <label for="">Email</label>
    <input type="email" required v-model="email">
    <label for="">password</label>
    <input type="password" required v-model="password" >

    <label for="">User Role_</label>
    <select v-model="roles">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>

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
      names:[]
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

</style>