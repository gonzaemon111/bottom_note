<template>
    <el-container style="height: 710px; border: 1px solid #eee">
    <el-aside width="200px" style="background-color: #E4E7ED">
        <el-menu :default-openeds="['1', '4']" background-color="#E4E7ED" text-color="#303133">
        <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>Messages</template>
            <el-menu-item-group>
            <template slot="title">Group 1</template>
            <el-menu-item index="1-1">Option 1</el-menu-item>
            <el-menu-item index="1-2">Option 2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="Group 2">
            <el-menu-item index="1-3">Option 3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
            <template slot="title">Option4</template>
            <el-menu-item index="1-4-1">Option 4-1</el-menu-item>
            </el-submenu>
        </el-submenu>
        <el-submenu index="2">
            <template slot="title"><i class="el-icon-document"></i>Documents</template>
            <el-menu-item-group>
            <template slot="title">Group 1</template>
            <el-menu-item index="2-1">Option 1</el-menu-item>
            <el-menu-item index="2-2">Option 2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="Group 2">
            <el-menu-item index="2-3">Option 3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="2-4">
            <template slot="title">Option 4</template>
            <el-menu-item index="2-4-1">Option 4-1</el-menu-item>
            </el-submenu>
        </el-submenu>
        <el-submenu index="3">
            <template slot="title"><i class="el-icon-view"></i>Groups</template>
            <el-menu-item index="1-1">情理底辺界隈</el-menu-item>
        </el-submenu>
        <el-submenu index="4">
            <template slot="title"><i class="el-icon-setting"></i>Setting</template>
            <el-menu-item index="3-1">Account</el-menu-item>
            <el-submenu index="3-4">
            <template slot="title">Option 4</template>
            <el-menu-item index="3-4-1">Option 4-1</el-menu-item>
            </el-submenu>
        </el-submenu>
        </el-menu>
    </el-aside>
    
    <!-- http://element.eleme.io/#/en-US/component/container#example　を参照 -->
    <el-container>
        <el-header style="text-align: right; font-size: 12px">
            <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect" background-color="#409EFF" text-color="#fff">
            <el-menu-item index="1">BottomNote</el-menu-item>
            </el-menu>
        </el-header>
        
        <el-main>
            <nuxt/>
        <el-table :data="tableData">
            <el-table-column prop="date" label="Date" width="140">
            </el-table-column>
            <el-table-column prop="author" label="Author" width="120">
            </el-table-column>
            <el-table-column prop="title" label="Title">
            </el-table-column>
        </el-table>
        </el-main>
    </el-container>
    </el-container>
</template>

<style>
  .el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
    padding: 0px;
  }
  
  .el-aside {
    color: #333;
  }
</style>

<script>
  export default {
    data() {
      const item = {
        date: '2016-05-02',
        author: 'Tom',
        title: 'プログラミング言語！'
      };
      // template内の:data="tableData"にArray(20).fill(item)をぶち込んでる。
      return {
        tableData: Array(20).fill(item)
      }
    }
  };
</script>