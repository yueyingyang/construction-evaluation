<template>
    <div>
        <div class="wrapper5" >
            <el-col>
              <span class="lebal">Lower Quantity</span>
              <el-input size="mini" style="width:100%" v-model="l_quantity" placeholder="请输入内容"></el-input>
              <span class="lebal">Average Repair Cost for Lower Quantity of</span>
              <el-input  size="mini" style="width:100%" v-model="aver_re_l" placeholder="请输入内容"></el-input>
              <span class="lebal">Upper Quantity</span>
              <el-input  size="mini" style="width:100%" v-model="u_quantity" placeholder="请输入内容"></el-input>
              <span class="lebal">Average Repair Cost for Upper Quantity of</span>
              <el-input size="mini" style="width:100%" v-model="aver_re_u" placeholder="请输入内容"></el-input>
              <span class="lebal">COV</span>
              <el-input size="mini" style="width:100%" v-model="COV" placeholder="请输入内容"></el-input>
          </el-col>
        </div>
        <div class="wrapper5">
            <el-col >
                <span class="lebal">项目编号</span>
                    <el-select size="mini" v-model="value0" placeholder="请选择">
                        <el-option
                            v-for="item in options0"
                            :key="item.value"
                            :label="item.label"
                            :value="item.value">
                        </el-option>
                    </el-select>
            </el-col>
            <schart class="wrapper" :canvasId="canvasId" :type="type" :data="data" :options="options"></schart>
        </div>
    </div>
</template>

<script>
    import Schart from 'vue-schart';
    export default {
        data() {
            return {
                COV: '',
                l_quantity: '',
                u_quantity: '',
                aver_re_l: '',
                aver_re_u: '',
                options0: [{
                    value: '选项1',
                    label: 'DB_Common'
                }, {
                    value: '选项2',
                    label: 'DB_School'
                }, {
                    value: '选项3',
                    label: 'DB_Hospital'
                }, {
                    value: '选项4',
                    label: 'DB_Office'
                }, {
                    value: '选项6',
                    label: 'DB_FEMA'
                }],
                value0:'',
                canvasId: 'myCanvas',
                type: 'line',
                data: [
                    {name: '2014', value: 1342},
                    {name: '2015', value: 2123},
                    {name: '2016', value: 1654},
                    {name: '2017', value: 1795},
                ],
                options: {
                    title: 'Total sales of stores in recent years'
                }
            }
        },


        components:{
          Schart
        }
    }
</script>


<style scoped>
    .wrapper5{
        position:relative;/*相对定位:参考物*/
        float: left;;/*浮动:左浮动 与父元素的左端对齐 依次的往右端显示 一行显示不下就换行接着依次显示*/
        top:5px;
        width:43%;
        height:300px;
        margin:18px 20px;
    
}


    .wrapper{
        width: 18rem;
        height: 18rem;
  }


    .lebal{
        position:relative;
        display: inline-block;
        padding:9px 0;
        color: #333;
    }

</style>