<script setup>
	import { RouterLink, RouterView } from "vue-router";
	import daySummaryData from "./components/daySummaryData.vue";
	import dayMonitorData from "./components/dayMonitorData.vue";
	import grap from "./components/graph.vue";
	import { ref } from "vue";
	const list = ref([
		"1） 《高速铁路设计规范》（TB10621-2014）",
		"2） 《铁路工程沉降变形观测与评估技术规程》（Q/CR 9230-2016）",
		"3） 《运营高速铁路基础变形监测管理办法》（铁总运[2015]113号）",
		"4） 《邻近铁路营业线施工安全监测技术规程》（TB10314-2021）",
		"5） 《高速铁路工程测量规范》（TB10601-2009）",
	]);
	const tableData = ref([
		{
			index: 1,
			paragraph: "桥梁段K126+248.15~K126+509.75，桥梁段K131+776.17~K132+070.47",
			isOK: "是",
			des: "",
		},
	]);
	const data = ref([
		{
			x: "±1.2mm",
			y: "±1.6mm",
			z: "±2.0mm",
		},
	]);
</script>

<template>
	<div class="title">
		<span
			><h1 class="title"><strong>监测日报</strong></h1></span
		>
		<span><h4>日期：2021年6月3日</h4></span>
		<br />
		<div>
			<h4><strong>监测依据:</strong></h4>
			<span v-for="item in list"> {{ item }}<br /> </span>
		</div>
		<br />
		<div>
			<h4>监测单位: 中铁第六勘察设计院集团有限公司</h4>
		</div>
		<br />
		<div>
			<h4>签发人:</h4>
		</div>
		<br />
		<div>
			<el-table
				:data="tableData"
				style="width: 1200px"
				:header-cell-style="{ 'text-align': 'center' }"
				:cell-style="{ 'text-align': 'center' }"
			>
				<el-table-column prop="index" label="序号" />
				<el-table-column prop="paragraph" label="监测段落" />
				<el-table-column prop="isOK" label="检测段落是否正常" />
				<el-table-column prop="des" label="备注" />
			</el-table>
		</div>
	</div>
	<br />
	<div class="box">
		<daySummaryData></daySummaryData>
	</div>
	<br />
	<div>
		<div>
			<span>临近既有线当日主要施工内容:</span
			><span>京广里程K126+346.25，K132+005.07，打桩机共2台，钻孔桩施工</span>
		</div>
		<div>
			<h4>当日主要施工内容照片:</h4>
			<div class="imgBox">
				<img src="../public/322b9d0b6fa6d382438e9936b7c8612b.png" alt="" />
			</div>
			<div class="imgBox">
				<img src="../public/75c3f3c5eb960f207e92534cf974c544.png" alt="" />
			</div>
		</div>
	</div>

	<br />
	<div class="box">
		<dayMonitorData></dayMonitorData>
	</div>
	<br />
	<div class="box">
		<grap></grap>
	</div>
	<br />
	<div class="box">
		<h4>监测结果分析:</h4>
		<daySummaryData></daySummaryData>
	</div>
	<br />
	<div class="box">
		<h4>
			监测阈值：(桥梁段水平位移
			（面向大里程方向，向左为负，向右为正）桥梁段竖向位移（向上为正，向下为负））)
		</h4>
		<h4></h4>
		<el-table
			:data="data"
			style="width: 800px"
			:header-cell-style="{ 'text-align': 'center' }"
			:cell-style="{ 'text-align': 'center' }"
		>
			<el-table-column prop="x" label="累计量预警值" />
			<el-table-column prop="y" label="累计量报警值" />
			<el-table-column prop="z" label="控制值" />
		</el-table>
	</div>
</template>

<style scoped>
	.title {
		display: block;
		width: 1200px;
	}
	.box {
		display: block;
		padding: 50px 0;
	}
	.imgBox {
		display: inline-block;
		padding: 20px;
	}
</style>
