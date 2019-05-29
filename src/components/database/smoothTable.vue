<template>
    <div class="smooth-table-container">
        <table v-if="fixexHeader&&fixedColumn">

        </table>
    </div>
</template>
<script>
export default {
    data(){
        return{
            columnData:[//最外层数据为第一行表头，第二行中的列为第一行中列的子集，第三行的列为第二行列的子集.....类似饿了吗的<column>多级标签嵌套

                {   //第一行，第一列（合并下一行2个子列,子列数据存放于此列的children数组）
                    field:'field1',
                    label:'第一行，第一列',
                    fixed:true,
                    width:100,
                    type:'edit',
                    repalceWithDom:null,
                    child:[//第一列的子列
                        { //第二行,第一列 
                            field:'field2-1',
                            label:'第二行,第一列',
                            width:100,
                            type:'edit',
                            repalceWithDom:null,
                            child:[//第二行,第一列的子列
                                { //第三行,第一列
                                    field:'field3-1',
                                    label:'第三行,第一列',
                                    width:100,
                                    type:'edit',
                                    repalceWithDom:null,
                                    child:[ ]
                                },
                                { //第三行,第二列
                                    field:'field3-2',
                                    label:'第三行,第二列',
                                    width:100,
                                    type:'edit',
                                    repalceWithDom:null,
                                    child:[ ]
                                },
                                { //第三行,第三列
                                    field:'field3-3',
                                    label:'第三行,第三列',
                                    width:100,
                                    type:'edit',
                                    repalceWithDom:null,
                                    child:[

                                    ]
                                }
                            ]
                        },
                        { //第二行 第二列
                            field:'field2-2',
                            label:'第二行 第二列',
                            width:100,
                            type:'edit',
                            repalceWithDom:null,
                            child:[
                                { //第三行,第四列
                                    field:'field3-4',
                                    label:'第三行,第四列',
                                    width:100,
                                    type:'edit',
                                    repalceWithDom:null,
                                    child:[

                                    ]
                                },
                                { //第三行,第五列
                                    field:'field3-5',
                                    label:'第三行,第五列',
                                    width:100,
                                    type:'edit',
                                    repalceWithDom:null,
                                    child:[

                                    ]
                                },
                                { //第三行,第六列
                                    field:'field3-6',
                                    label:'第三行,第六列',
                                    width:100,
                                    type:'edit',
                                    repalceWithDom:null,
                                    child:[

                                    ]
                                }
                            ]
                        }
                    ]
                },
                {   //第一行，第二列
                    field:'field1-2',
                    label:'第一行，第二列',
                    fixed:false,
                    width:100,
                    type:'edit',
                    repalceWithDom:null,
                    child:[
                        {
                            field:'field2-3',
                            label:'第二行第三列',
                            fixed:false,
                            width:100,
                            type:'edit',
                            repalceWithDom:null,
                            child:[
                                {
                                    field:'field2-7',
                                    label:'第三行第七列',
                                    fixed:false,
                                    width:100,
                                    type:'edit',
                                    repalceWithDom:null,
                                    child:[]

                                }
                            ]
                        }
                    ]
                },
                {   //第一行，第三列
                    field:'field1',
                    label:'第一行，第三列',
                    fixed:false,
                    width:100,
                    type:'edit',
                    repalceWithDom:null,
                    rowspan:2,
                    child:[//如果有rowspan 则视为此单元格下一级与这一级合并，children为此单元格第rowspan级子节点
                        {   //第三行，第四列
                            field:'field1',
                            label:'',
                            width:100,
                            type:'edit',
                            repalceWithDom:null,
                            rowspan:2,
                            child:[]
                        },
                    ]
                },
                {
                   //第一行，第四列
                    field:'field1',
                    label:'第一行，第四列',
                    fixed:false,
                    width:100,
                    type:'edit',
                    rowspan:3,
                    repalceWithDom:null,
                    rowspan:2,
                    child:[] 
                }
            ],//列数据
            rowData:[
                { }
            ],//行数据

            fixedHeader:true,//是否冻结表头
            fixedColumn:false,//是否有冻结列
            fixedHeaderAndColumnTable:[],//冻结表头和冻结列交汇的部分
            fixedHeaderTable:[],//冻结表头部分
            fixedColumnTable:[],//冻结列部分
            scrollTable:[],//非冻结区域

        }
    },
    methods:{
        initColumn(){
            function findLastHeaderRow(){//找到表头最后一行所有元素

            }
            //查找是否有列需要冻结，如果有，将需要冻结的列放到最前方
            let freezeColumn=[];
            for(let i=0;i<this.columnData.length;i++){
                if(this.columnData[i].fiexd){
                    freezeColumn.push(this.columnData[i]);
                }
            }
            if(freezeColumn.length){
                this.fixedColumn=true;
                if(fixedHeader){

                }
            }
        }
    }
}
</script>
<style lang="less" scoped>

</style>
