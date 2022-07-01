<template>
  <div id="app">
    <el-container>
      <el-header class="classifyBar">
        <el-row>
          <el-col :span="12"><div class="icon"></div></el-col>
          <el-col :span="12">
            <el-row class="classifyTitle">
              <el-col :span="6"><span>ElementUI</span></el-col>
              <el-col :span="6"><span>Vuex</span></el-col>
              <el-col :span="6"><span>Echarts</span></el-col>
              <el-col :span="6"><span>待完善</span></el-col>
            </el-row>
          </el-col>
        </el-row>
      </el-header>
      <el-container>
        <el-header></el-header>
        <el-main>
          <excel-to-json></excel-to-json>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import ExcelToJson from './components/ExcelToJson.vue'
export default {
  name: 'App',
  components: {
    ExcelToJson
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
}
.classifyBar{
  width:100%;
  height:120px;
}
.icon{
  margin-left:30px;
  width: 100px;
  height:120px;
  /* background: url('./assets/img/Gabriel.png') no-repeat 100%;
  background-size: cover; */
}
.classifyTitle{
  margin-top: 30px;
}
</style>
