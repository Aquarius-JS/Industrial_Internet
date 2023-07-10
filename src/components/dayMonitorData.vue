<script setup>
	import { ref } from "vue";
	defineProps(["dayMonitorData"]);
	const data = ref("2023年6月3日");
	const dayMonitorData = ref([
		{
			pierNum: 28,
			desc: "K126+248.15",
			z: {
				sum: "1.0",
				day: "0.0",
			},
			x: {
				sum: "0.4",
				day: "0.0",
			},
			y: {
				sum: "-0.2",
				day: "0.0",
			},
		},
		{
			pierNum: 29,
			desc: "K126+280.85",
			z: {
				sum: "-0.2",
				day: "0.0",
			},
			x: {
				sum: "0.4",
				day: "0.0",
			},
			y: {
				sum: "0.6",
				day: "0.0",
			},
		},
		{
			pierNum: 30,
			desc: "K126+313.55",
			z: {
				sum: "0.7",
				day: "0.0",
			},
			x: {
				sum: "0.4",
				day: "0.0",
			},
			y: {
				sum: "0.1",
				day: "0.0",
			},
		},
		{
			pierNum: 31,
			desc: "K126+346.25",
			z: {
				sum: "-0.2",
				day: "0.0",
			},
			x: {
				sum: "0.3",
				day: "0.0",
			},
			y: {
				sum: "0.6",
				day: "0.0",
			},
		},
		{
			pierNum: 32,
			desc: "K126+378.95",
			z: {
				sum: "-1.1",
				day: "0.0",
			},
			x: {
				sum: "0.5",
				day: "0.0",
			},
			y: {
				sum: "-0.2",
				day: "0.0",
			},
		},
		{
			pierNum: 33,
			desc: "K126+411.65",
			z: {
				sum: "-1.0",
				day: "0.0",
			},
			x: {
				sum: "-0.4",
				day: "0.0",
			},
			y: {
				sum: "-0.6",
				day: "0.0",
			},
		},
		{
			pierNum: 34,
			desc: "K126+444.35",
			z: {
				sum: "0.1",
				day: "0.0",
			},
			x: {
				sum: "0.7",
				day: "0.1",
			},
			y: {
				sum: "0.3",
				day: "0.0",
			},
		},
		{
			pierNum: 35,
			desc: "K126+477.05",
			z: {
				sum: "0.2",
				day: "0.2",
			},
			x: {
				sum: "0.2",
				day: "0.0",
			},
			y: {
				sum: "0.1",
				day: "0.0",
			},
		},
		{
			pierNum: 36,
			desc: "K126+509.75",
			z: {
				sum: "0.3",
				day: "0.2",
			},
			x: {
				sum: "0.5",
				day: "0.4",
			},
			y: {
				sum: "0.2",
				day: "0.0",
			},
		},
	]);
</script>

<template>
	<el-table
		:data="dayMonitorData"
		style="width: 1200px"
		:header-cell-style="{ 'text-align': 'center' }"
		:cell-style="{ 'text-align': 'center' }"
	>
		<el-table-column :label="'监测日报  ' + data">
			<el-table-column label="点名">
				<el-table-column label="京广墩号" prop="pierNum" />
				<el-table-column label="京广里程" prop="desc" />
			</el-table-column>

			<el-table-column label="竖向位移/mm">
				<el-table-column label="累计位移" prop="z.sum" />
				<el-table-column label="日位移量" prop="z.day" />
			</el-table-column>

			<el-table-column label="水平位移(纵桥向)/mm">
				<el-table-column label="累计位移" prop="x.sum" />
				<el-table-column label="日位移量" prop="x.day" />
			</el-table-column>

			<el-table-column label="水平位移(横桥向)/mm">
				<el-table-column label="累计位移" prop="y.sum" />
				<el-table-column label="日位移量" prop="y.day" />
			</el-table-column>
		</el-table-column>
	</el-table>
</template>

<style></style>
