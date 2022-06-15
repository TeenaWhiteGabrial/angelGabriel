/* 
<template>
    <div>
        <input id="fileInput" type="file" @change="excelToJson" style="display: none;">
        <el-button @click="clickInupt">点击上传</el-button>
        <span>{{fileName}}</span>
        <div><span v-for="(item,index) in fileData" :key="index">{{item}},<br/></span></div>
    </div>
</template>
<script>
    import XLSX from './importComponents/xlsx.core.min.js'
    export default {
        data(){
            return {
                fileName:'',
                fileData:{}
            }
        },
        methods:{
            clickInupt(){
                document.querySelector('#fileInput').click();
            },
            excelToJson(){
                let vue=this;
                var files = document.querySelector('#fileInput').files;
                vue.fileName=files[0].name;
                var fileReader = new FileReader(); // 将文件内容读入内存
                fileReader.readAsBinaryString(files[0]);
                fileReader.onload = function (ev) { // 当读取操作成功完成时调用
                    try {
                        var data = ev.target.result,
                            workbook = XLSX.read(data, { type: 'binary' });
                    } catch (e) {
                        alert('文件类型不正确');
                        return;
                    }
                    for(var sheet in workbook.Sheets){
                        vue.fileData =(XLSX.utils.sheet_to_json(workbook.Sheets[sheet]));
                    }
                };
            }
        }
    }
</script>

<style scoped>

</style>