<template>
    <div class="login-wrap">
        <div class="login-entangle">
            <p class="login-left">
                  Lead Investor
            </p>
            <p class="login-center">
                Financial investment
            </p>
            <div class="login-bottom">
                <span class="left-fir">
                    高效
                </span>
                <span class="left-dot">
                    
                </span>
                <span class="left-sec">
                    信任
                </span>
                <span class="right-dot"></span>
                <span class="left-thi">
                    依赖
                </span>
            </div>           
        </div>
        <div class="login-right">
            <p class="login-name">
                企业登录
            </p>
            <div class="login-zhanghao">
                <span>
                <img src="/static/img/账号.png" class="icon-fir">
                </span>
                <input type="text" placeholder="请输入账号/手机号" class="user-name"/>
            </div>
            <div class="login-mima">
                 <span>
                 <img src="/static/img/密码.png" class="icon-sec">
                 </span>
                 <input type="password" placeholder="请输入密码" class="user-pass" />
            </div>
            <div>
                 <a href="#" class="password-seach">找回密码</a>    
                 <a href="#" class="registration">企业注册</a> 
            </div>    
            <button class="register">登录</button> 
            <hr class="line-bottom" />
            
        </div>
       
       
    </div>
</template>

<script>
    export default {
        data: function(){
            return {
                ruleForm: {
                    username: '',
                    password: ''
                },
                rules: {
                    username: [
                        { required: true, message: '请输入用户名', trigger: 'blur' }
                    ],
                    password: [
                        { required: true, message: '请输入密码', trigger: 'blur' }
                    ]
                }
            }
        },
        methods: {
            submitForm(formName) {
                const self = this;
                self.$refs[formName].validate((valid) => {
                    if (valid) {
                        localStorage.setItem('ms_username',self.ruleForm.username);
                        self.$router.push('/readme');
                    } else {
                        console.log('error submit!!');
                        return false;
                    }
                });
            }
        }
    }
</script>

<style scoped>
   html,body{
    width: 100%;
    height: 100%;
   }
    .login-wrap{
        position: relative;
        width:1440px;
        height: 900px;
        background: url(/static/img/bg.png);
        background-size: 100% 100%;
        background-repeat: no-repeat;
        margin: 0 auto;
    }
    .ms-title{
        position: absolute;
        top:50%;
        width:100%;
        margin-top: -230px;
        text-align: center;
        font-size:30px;
        color: #fff;

    }
    .ms-login{
        position: absolute;
        left:50%;
        top:50%;
        width:300px;
        height:160px;
        margin:-150px 0 0 -190px;
        padding:40px;
        border-radius: 5px;
        background: #fff;
    }
    .login-btn{
        text-align: center;
    }
    .login-btn button{
        width:100%;
        height:36px;
    }
    .login-left{
       /* position: absolute;*/
       /* top: 180px;
        left: 110px;*/
        font-size: 96px;
        color: #fff;
        font-family: ITC Avant Garda Gothic Demi Regular;
    }
    .login-center{
        font-size: 40px;
        color: #afacae;
        /*position: absolute;*/
        /*top: 300px;*/
        /*left: 110px;*/
       /* margin-top: 24px;*/
    }
    span{
        color: #aca7a7;
       /* position: absolute;*/
    }
    .left-fir{
        top: 800px;
    }
    .login-entangle{
        position: absolute;
        top: 180px;
        left: 110px;
        width: 620px;
    }
    .login-bottom{
        font-size: 28px;
        margin-top: 42px;
    }
    .left-sec{
        margin-left: 30px;
    }
    .left-thi{
        margin-left: 30px;
    }
    .left-dot,.right-dot{
        width: 8px;
        height: 8px;
        border-radius: 50%;
        background-color: #aca7a7;
        display: inline-block;
        margin-left: 20px;
        margin-bottom: 5px;
    }
   .ms-login{
        margin-left: 10px;
        margin-top: 48px;
   }
   .login-right{
        position: absolute;
        top: 280px;
        left: 800px;
   }
   .login-name{
        color: #fff;
        font-size: 28px;
        /*margin-left: 240px;*/
   }
    .login-right{
        text-align: center;
        margin-left: 200px;
        clear: both;
    }
    .user-name{
        width: 300px;
        height: 80px;
        border: none;
        background: transparent; 
        color: #fff;
        font-size: 20px;
        /*background-image: url(/static/img/账号.png);*/
        /*background-repeat: no-repeat;*/
        /*background-position: 0% 50%;*/
        border-bottom: solid 2px #a6a9ad;
        border-left: none;
        border-top: none;
        border-right: none;
        outline: none;
    }
    .user-pass{
        width: 300px;
        height: 80px;
        /*border: none;*/
        background: transparent; 
        color: #fff;
        font-size: 20px;
       /* background-image: url(/static/img/密码.png);
        background-repeat: no-repeat;
        background-position: 0% 50%;*/
        border-bottom: solid 2px #a6a9ad;
        border-left: none;
        border-top: none;
        border-right: none;
        outline: none;
    }
     input::-webkit-input-placeholder{
        color: #a6a9ad;
     }
     .icon-fir{
        /*margin-top: 50px;*/
     }
     .login-zhanghao img{
        position: absolute;
        top: 60px;
        left: -40px;
     }
     .login-mima img{
        position: absolute;
        top: 140px;
        left: -40px;
     }
     a{
        color: #fff;
        font-size: 16px;
        margin-top: 16px;
        display: inline-block;
     }
     .password-seach{
        float: left;
     }
     .registration{
        float: right;
     }
     .register{
        width: 300px;
        height: 54px;
        margin-top: 42px;
        border-radius: 30px;
        background: #f05e5e;
        border: none;
        color: #fff;
        font-size: 22px;
        /*font-family: "微软雅黑";*/
        outline: none;
     }
     .line-bottom{
        margin-top: 24px;
        border: solid 1px #a6a9ad;
        /*background: green;*/
     }
</style>