<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="less">
*{
	box-sizing: border-box;
	padding: 0;
	margin: 0;
	text-decoration: none;
	list-style-type: none;
}
::-webkit-scrollbar {
  /*滚动条整体样式*/
  width : 0px;  /*高宽分别对应横竖滚动条的尺寸*/
  height: 0px;
}
::-webkit-scrollbar-thumb {
  /*滚动条里面小方块*/
  border-radius: 0px;
  box-shadow   : inset 0 0 5px rgba(0, 0, 0, 0.2);
  background   : white;
}
::-webkit-scrollbar-track {
  /*滚动条里面轨道*/
  box-shadow   : inset 0 0 0px rgba(0, 0, 0, 0.2);
  border-radius: 0px;
  background   : #ededed;
}
.ant-form-explain, .ant-form-extra{
  text-align:left!important;
}
.txt-right{
	text-align: right;
}
.mr-b{
	margin-bottom: 10px;
}
.mr-t{
	margin-top: 10px;
}
.mr-l{
	margin-left: 10px;
}
.mr-r{
	margin-right: 10px;
}
.ant-layout-sider-children{
	overflow-y: auto;
}
.flex {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
}

.flex-row {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    -webkit-box-orient: horizontal;
    flex-direction: row;
}

.flex-col {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    -webkit-box-orient: vertical;
    flex-direction: column;
}

.flex-grow-0 {
    min-width: 0;
    -webkit-box-flex: 0;
    -ms-flex-positive: 0;
    flex-grow: 0;
    -ms-flex-negative: 0;
    flex-shrink: 0;
   
}

.flex-grow-1 {
    min-width: 0;
    -webkit-box-flex: 1;
    -ms-flex-positive: 1;
    flex-grow: 1;
    -ms-flex-negative: 1;
    flex-shrink: 1;
}

.flex-x-center {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
}
.flex-x-spacebetween {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    justify-content: space-between;
}
.flex-x-spacearound{
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    justify-content: space-around;
}
.flex-x-start{
	display: -webkit-box;
	display: -webkit-flex;
	display: flex;
	justify-content: flex-start;
}
.flex-x-end{
	display: -webkit-box;
	display: -webkit-flex;
	display: flex;
	justify-content: flex-end;
}
.flex-y-center {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    -ms-grid-row-align: center;
    align-items: center;
}

.flex-y-bottom {
    display: -webkit-box;
    display: -webkit-flex;
    display: flex;
    -webkit-box-align: end;
    -ms-flex-align: end;
    -ms-grid-row-align: flex-end;
    align-items: flex-end;
}
.bg-img{
	background-position: 50% 50%;
	background-repeat: no-repeat;
	background-size: 100%;
	background-color: #D8D8D8;
}
.txt-center{
	text-align: center;
}
.el-table .cell.el-tooltip>div{
	overflow: hidden;
	text-overflow: ellipsis;
	white-space: nowrap;
}
</style>
