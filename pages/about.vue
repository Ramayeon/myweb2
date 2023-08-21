<template>


    <div class="d-flex justify-content-center" style="margin-top: 5%; ">
    <div class="card mb-3" style="max-width: 750px; box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;" >
  <div class="row g-0">
    <div class="col-md-4">
      <img src="https://rms.tatc.ac.th/files/importpicstd/01/66309010020.jpg" class="img-fluid rounded-start" alt="...">
    </div>
    <div class="col-md-8">
      <div class="card-body">
        <h5 class="card-title">ข้อมูลส่วนตัว</h5>
    <input type="text" @input="setNickname">
    <p>ชื่อเล่น : {{ nickname }}</p>
    <p>ชื่อ : {{ firstname }}</p>
    <p>นามสกุล : {{ lastname }}</p>
    <p>อายุ : {{ age }}</p>
    <p>ที่อยู่ : <span v-html="address"></span></p>

    <p v-if="hobby.length ===0" >ไม่มีงานอดิเรก</p>
    <div v-else>
    <p>งานอดิเรก :</p>
        <ul>
            <li v-for="item in hobby">{{ item }}</li>
        </ul>
    </div>
      
        <p>ข้อมูลพื้นฐาน :</p>
        <ul>
            <li v-for="(value,key) in general" :key="key">{{key}} : {{ value }}</li>
        </ul>
       
        <button @click="showData">คลิกเพื่อดูข้อมูล</button>
        <button @click="increment(10)">เพิ่มค่า</button>
        <button @click="decrement(3)">ลดค่า</button>
        <button type="submit">บันทึก</button>
        

      </div>
    </div>
  </div>
</div>
</div>





    <div>
   


    </div>
    </template>
    <script>
    export default {
    data() {
      return {
        firstname:"Athithat",
        lastname: "Noreewan",
        age: 18,
        address: "<i>Sriracha</i>",
        picture: "https://rms.tatc.ac.th/files/importpicstd/01/66309010020.jpg",
        size: 250,
        hobby : ["ทำสวน","นอน"],
        general : {gender:"ชาย",weight : 55.5,height:172.5,status:false},
        nickname :'',
      }
    
    },
    methods: {
        getfullname(){
        return `$(this.fristname) $(this.lastname)`
    },
    showData(){
        alert(this.firstname)
            },
    increment(value){
        this.age += value
    },
    decrement(value){
        this.age -= value
    },
    setNickname(event){
        this.nickname=event.target.value
    },
    submitForm(){
        
        alert('บันทึกข้อมูลเรียบร้อย')
    }
        }
    };
</script>

<style>
body{
    background-image: linear-gradient(to right top, #051937, #004d7a, #008793, #00bf72, #a8eb12);
}
</style>