<template>
  <div class="title">欢迎来到知食分子！</div>
  <!-- <form action=""></form> <form action=""></form> -->

  <div class="explainSen">
    <p class="exSen1">· 为提供优质服务，知食分子需获取您的公开信息</p>
    <p class="exSen2">授权微信头像&昵称</p>
  </div>

  <button type="submit" style="height:50px;width:80%" v-on:click="toLabel">授权进入知食分子</button>

  <image class="brand" src="/static/logosquare.jpg"></image>
  
  <div class="Agreement">
    <label class="Pick"><checkbox color="#F79709" style="transform: scale(0.6);" checked></checkbox></label>
    <span class="pickSent">选中代表您已同意</span>
    <span class="userAgree">《用户服务协议》</span>
    <span class="privacyAgree">《隐私权政策》</span>
  </div>
</template>


<script>
export default {
  onLoad() {
    uni.setStorage({key:"id", data:"小明"})
  },
  methods: {
    toLabel: () => {               //跳转到登录页面
      uni.navigateTo({
        url: '../labelpage/index'
      })
    }
  },
}
</script>

<style scoped>

  .title{
    margin-top: 10%;
    text-align: center;
    margin-left:7%;
    font-size: 60rpx;
    font-family:FZYaoti , Arial, sans-serif;
    font-weight: normal;
    letter-spacing: 2.5px;
  }

  .exSen1{
    position: absolute;
    margin-top:62%;
    margin-left:8%;
    font-weight: 80;
    color: rgb(0, 0, 0);
    font-size: 12px;
    font-family:  Arial, sans-serif ;
    font-weight: 550;
  }
  .exSen2{
    position: absolute;
    margin-top:70%;
    margin-left:11%;
    font-weight: 100;
    color: rgb(117, 114, 114);
    font-size: 12px;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif ;
    z-index: 1;
  }

  /*Button*/
  button {
    position: relative;
    margin-top: 80%;
    padding: 1.3em 1.3em;
    font-size: 16px;
    margin-left: 10%;
    text-transform: uppercase;
    letter-spacing: 2.5px;
    font-weight: 550;
    color: #000;
    background-color: rgb(255, 193, 37);
    border: none;
    border-radius: 45px;
    box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease 0s;
    cursor: pointer;
    outline: none;
    line-height:40%;  /*button中字体居中*/
}

button:hover {
  background-color: #F79709;
  box-shadow: 0px 15px 20px rgba(204, 143, 51, 0.6);
  color: #fff;
  transform: translateY(-7px);
}

button:active {
  transform: translateY(-1px);
}


/*agreePick*/

.Pick{
  position: absolute;
  margin-top: 49%;
  margin-left: 5%;
  font-size: 11px;
}
.pickSent{
  position: fixed;
  margin-top: 50%;
  margin-left: 13%;
  font-size: 11px;
}
.userAgree{
  position:absolute;
  margin-left:45%;
  margin-top: 50%;
  font-size: 11px;
  color: #F79709;
}
.privacyAgree{
  position:absolute;
  margin-left:73%;
  margin-top: 50%;
  font-size: 11px;
  color: #F79709;
}

/*logo*/
.brand {
  height: 250rpx;
  width: 250rpx;
  border-radius:200px;
  position: fixed;
  top: 18%;
  left: 33%;
  box-shadow: 1px 4px 10px 1px rgba(247,151,9,0.7);/*阴影*/
}
@keyframes roll{/*创建一个动画*/
				from{ transform: rotate(-15deg);}
				to{ transform: rotate(15deg);}
}
.brand:hover{/*鼠标移上去时,设置样式*/
  animation: roll 1.8s ;/*调用动画*/
}	 

</style>