<template>
  <div id="home">
    <div class="title">
      小仙女验证系统
    </div>
    <div class="content">
      <div class="tip-text">
        请输入小仙女的名字：
      </div>
      <div class="name-input">
        <p><input type="text" v-model="name" v-on:keyup.enter="verifyName"></p>
        <p><button @click="verifyName">确定</button></p>
      </div>
    </div>

    <div class="mask-layer" v-if="alertFlag">
      <div class="alert-main">
        <div class="close-button">
          <button @click="closeAlert">×</button>
        </div>
        <div class="alert-content">
          <div :class="isName? classB : classA">{{ alertInfo }}</div>
          <div class="alert-button">
            <button @click="closeAlert">确定</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const info = ["输入的小仙女名字不正确哦~",
              "这可能是其他小仙女的名字哦~",
              "请输入正确的小仙女名字~",
              "这是哪个小仙女？不对哦~",
              "名字不对哦，再仔细想想~",
              "警告！小仙女的名字被你输错啦~",
              "再想想，这是真正的小仙女吗？",
              "呀！这个名字好像不对哦~"]
export default {
  name: 'Hello',
  data () {
    return {
      name: "",
      alertFlag: false,
      alertInfo:"",
      isName: false,
      classA: "alert-textA",
      classB: "alert-textB"
    }
  },

  methods: {
    closeAlert() {
      this.alertFlag = false;
      this.isName = false;
      this.alertInfo = "";
    },
    verifyName() {
      if(this.name === "") {
        this.alertInfo = "姓名不能为空！";
        this.alertFlag = true;
      } else if(this.name === "李建红") {
        this.isName = true;
        this.alertInfo = "小仙女，就是你啦！";
        this.alertFlag = true;
      } else {
        let idx = Math.floor(Math.random()*8);
        this.alertInfo = info[idx];
        this.alertFlag = true;
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #home {
    height: 100%;
    background: #343a40;
    vertical-align: middle;
    text-align: center;
  }

  .title {
    width: 100%;
    color: white;
    font-size: 35px;
    font-weight: bold;
    font-family: "LiSu";
    position: relative;
    top: 30%;
    letter-spacing: 10px;
  }

  .content {
    width: 100%;
    position: relative;
    top: 35%;
  }

  .tip-text {
    display: block;
    width: 100%;
    color: white;
    font-family: "楷体";
    font-size: 30px;
    font-weight: bold;
  }

  .name-input {
    margin-top: 15px;
  }

  .name-input input {
    width: 300px;
    height: 30px;
    margin: 0;
    padding: 0;
    border: 1px;
    border-radius: 5px;
    outline: none;
    text-align: center;
    font-size: 20px;
    font-weight: bold;
    font-family: "楷体";
    color: #993366;
  }

  .name-input button {
    width: 150px;
    height: 40px;
    background: #28a745;
    color: white;
    border: 1px;
    outline: none;
    border-radius: 5px;
    font-size: 25px;
    font-weight: bold;
    font-family: "楷体";
    letter-spacing: 10px;
  }

  .name-input button:hover {
    background: #0066FF;
  }

  .mask-layer {
    height: 100%;
    width: 100%;
    background:rgba(0,0,0,0.8);
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 500;
  }

  .alert-main {
    height: 200px;
    width: 350px;
  }

  .close-button {
    width: 350px;
    height: 30px;
    background: grey;
    border: 0px solid #343a40;
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
    text-align: right;
  }

  .close-button button {
    height: 30px;
    width: 30px;
    outline: none;
    margin: 0;
    padding: 0;
    border: 0;
    background: none;
    color: white;
    font-size: 25px;
  }

  .close-button button:hover {
    background: #dc3545;
  }

  .alert-content {
    width: 350px;
    height: 170px;
    background: #E0E0E0;
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
  }

  .alert-textA {
    width: 100%;
    height: 30px;
    position: relative;
    top: 50px;
    font-size: 20px;
    color: #181818;
  }
  .alert-textB {
    width: 100%;
    height: 30px;
    position: relative;
    top: 50px;
    font-size: 20px;
    font-weight: bold;
    color: #28a745;
  }
  .alert-button {
    width: 100%;
    height: 30px;
    position: relative;
    top: 65px;
    text-align: right;
  }
  .alert-button button {
    width: 80px;
    height: 40px;
    background: #B8B8B8;
    margin-right: 15px;
    padding: 0;
    border: 0px solid;
    border-radius: 5px;
    outline: none;
    font-size: 20px;
    color: #181818;
  }
  .alert-button button:hover {
    background: #A0A0A0;
  }

</style>
