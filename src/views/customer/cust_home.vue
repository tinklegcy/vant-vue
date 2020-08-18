<template>
    <div class="cust_home">
        <van-row type="flex">
            <van-col span="6">span: 6</van-col>
            <van-col span="6">span: 6</van-col>
            <van-col span="6">span: 6</van-col>
        </van-row>
        <span class="sp-st">1111</span>
        <div class = "top_div">
            <div class="div1">
                <div class = "div1_1">头像</div>
                <div class = "div1_2">
                    <div class = "div1_2_1">
                        <div class = "word_1">刘德华</div>
                        <div class = "word_2">厅堂主管</div>
                    </div>
                    <div class = "div1_2_2 word_3">昌平分行回龙观东大街支行</div>
                    <div class = "div1_2_3 word_4">经验丰富 ｜ 专业认证 ｜ 定制服务</div>
                </div>
            </div>
           <div class="div2">
                <div>展开</div>
                <div>加为好友</div>
            </div>
        </div>
        <div class = "div1">
            <p>资讯指标</p>
        </div>
        <div class = "div1">
            <p>海报</p>
        </div>
        <div class = "div1">
            <p>产品资讯列表</p>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.cust_home .top_div{
    border: 1px solid red;
    height: 300px;
    margin: 40px 30px;
    padding: 20px 30px;
    display: flex;
    flex-direction:column;
    /* justify-content: space-between; */
}
.cust_home .div1{
    height: 158px;
    display: flex;
    justify-content: flex-start;
}
.cust_home .div1 .div1_1{
    border: 1px solid red;
    width: 158px;
}
.cust_home .div1 .div1_2{
    border: 1px solid red;
    margin-left: 15px;
    display: flex;
    flex-direction:column;
}
.cust_home .div1 .div1_2_1{
  display: flex;
  justify-content: flex-start;
  align-items:flex-end;
}
.cust_home .div2{
    margin-top: 21.5px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
}
.word_1{
    font-size:36px;
    font-family:PingFangSC-Medium,PingFang SC;
    font-weight:500;
    color:rgba(51,51,51,1);
    line-height:50px;
}
.word_2{
    font-size:24px;
    font-family:PingFangSC-Regular,PingFang SC;
    font-weight:400;
    color:rgba(51,51,51,1);
    line-height:33px;
}
.sp-st {
 font-size:30px;

}
</style>
