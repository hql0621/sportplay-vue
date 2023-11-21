<template>
    <div>
      <el-card>



          <!-- 用户列表 border边框 stripe隔行变色 -->
          <el-table :data="responseData" :border="true" stripe>
              <el-table-column type="index"></el-table-column><!-- 索引列 -->
              <el-table-column label="用户名" prop="researched_person_id"></el-table-column>
              <el-table-column label="体温" prop="temperature"></el-table-column>
              <el-table-column label="家庭" prop="family_user_id"></el-table-column>
              
              
                
          </el-table>


</el-card> 
    </div>
</template>
<script>
import axios from 'axios';


export default {
  data() {
    return {
      responseData: null
    };
  },
  methods: {
    },
  created() {
    const apiUrl = "http://www.pahealthsys.cn/device/deviceData/getDataByType";

    const requestData = {
      current: 1, // 第几页
      size: 40, // 每页多少条
      startDate: "", // 开始日期，可以根据需要填写
      endDate: "", // 结束日期，可以根据需要填写
      type: "temperature", // 数据类型
    };

    const requestOptions = {
      method: "POST",
      headers: {
        Authorization: "Bearer 83e60402-b255-4f7d-87ac-139c6564f250",
        "Content-Type": "application/json",
      },
      body: JSON.stringify(requestData),
    };

    fetch(apiUrl, requestOptions)
      .then((response) => response.json())
      .then((data) => {
        if (data.code === 0) {
          const healthData = data.data.records;
          console.log(healthData); // 在这里处理健康数据
          this.responseData=healthData;
        } else {
          console.error("请求失败:", data.msg);
        }
      })
      .catch((error) => {
        console.error("请求失败:", error);
      });
  }
};
</script>
<style lang="less" scoped>

</style>