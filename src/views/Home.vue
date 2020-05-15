<template>
  <div class="home">
    <el-row :gutter='15'>
      <el-col :span="6">
        <h1 class="tit">全部书籍</h1>
        <div v-for='item in list' :key="item.id" class="ltBox">
          <h3>{{item.title}}</h3>
          <p v-for='sub in item.books' :key='sub.id' class="bookMenu">
            {{sub.name}}
          </p>
        </div>
       
        </el-col>
      <el-col :span="18">
        <div class="img"></div>
        <!-- 卡片 -->
         <el-row :gutter='10'>
          <el-col :span="12" v-for="(o) in cadrs" :key="o">
            <el-card :body-style="{ padding: '0px' }">
              <el-row>
                <!-- 左侧图片 -->
                <el-col :span='6'>
                  <img src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png" width="100%" class="image">
                </el-col>
                <el-col :span='18'>
                  <span class="cards_tit">{{o.title}}</span>
                  <p class="cards_tit">{{o.text}}</p>
                  <el-button type="primary" size='mini' class="buyBtn" @click="clickHandle(o.id)">立即购买</el-button>
                </el-col>
              </el-row>
            </el-card>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
   <MainPage />
  </div>
</template>
<script>
// @ is an alias to /src

export default {
  data(){
    return{
      list:[
        {
          id:1,
          title:'移动互联网开发专业书籍',
          books:[
            {
              id:'dlp1',
              name:'web标准网页设计之道',
            },
            {
              id:'dlp2',
              name:'Photoshop商业网站设计',
            },
            {
              id:'dlp3',
              name:'C#程序设计',
            },
            {
              id:'dlp4',
              name:'Spl server数据库基础',
            },
            {
              id:'dlp5',
              name:'C#桌面应用程序开发',
            },
            {
              id:'dlp6',
              name:'Java语言基础',
            },
            {
              id:'dlp7',
              name:'Java面向对象编程',
            },
            {
              id:'dlp8',
              name:'Java语言高级特性',
            },
          ]
        },
        {
          id:2,
          title:'移动互联网应用专业书籍',
            books:[
            {
              id:'apl1',
              name:'计算机基础应用',
            },
            {
              id:'apl2',
              name:'linux系统管理',
            },
            {
              id:'apl3',
              name:'企业网络互联技术',
            },
            {
              id:'apl4',
              name:'windows网络服务管理',
            },
            {
              id:'apl5',
              name:'windows系统管理',
            },
            {
              id:'apl6',
              name:'windows活动目录管理',
            },
            {
              id:'apl7',
              name:'计算机网络技术',
            },
          ]
        }
      ],
      //卡片
      cadrs:[
        {
          id:1,
          title:'移动互联网开发全套书籍',
          img:'',
          text:'Element 额外提供了一系列类名，用于在某些条件下隐藏元素。这些类名可以添加在任何 DOM 元素或自定义组件上。如果需要，请自行引入以下文件'
        },
        {
          id:2,
          title:'移动互联网应用全套书籍',
          img:'',
          text:'Element 额外提供了一系列类名，用于在某些条件下隐藏元素。这些类名可以添加在任何 DOM 元素或自定义组件上。如果需要，请自行引入以下文件'
        },
        {
          id:3,
          title:'大数据全套书籍',
          img:'',
          text:'Element 额外提供了一系列类名，用于在某些条件下隐藏元素。这些类名可以添加在任何 DOM 元素或自定义组件上。如果需要，请自行引入以下文件'
        },
        {
          id:4,
          title:'人工智能全套书籍',
          img:'',
          text:'Element 额外提供了一系列类名，用于在某些条件下隐藏元素。这些类名可以添加在任何 DOM 元素或自定义组件上。如果需要，请自行引入以下文件'
        },
      ]
    }
  },
    methods:{
      clickHandle(id){
        this.$router.push({
          name:'Detail',
          params:{
            id:id,
          }
        })
      }
    }
}
</script>
<style lang="scss" scoped>
.tit{
  height: 40px;
  line-height: 40px;
  color: #fff;
  background: navy;
   }
.ltBox{
  background:#fff;
  margin-bottom: 3px;
   .bookMenu{
     height: 30px;
     line-height: 30px;
     font-size: 16px;
   }
}
.img{
  height:300px;
  background: orangered;
}
.buyBtn{
  margin: 10px 0 0 10px;
}
</style>
