<script setup>
	import { ref } from "vue";
	defineProps(["dataList"]);
	const data = ref("2023年6月3日");
	const dataList = ref([
		{
			//桥梁段
			name: "K126+248.15~K126+509.75",
			//日位移
			day: {
				//竖向位移
				z: {
					//变化范围
					data: "0~0.2",
					//最大值出现位置
					location: "K126+509.75",
				},
				x: {
					//变化范围
					data: "-0.2~0.2",
					//最大值出现位置
					location: "K126+509.75",
				},
				y: {
					//变化范围
					data: "0.0~0.0",
					//最大值出现位置
					location: "K126+509.75",
				},
			},
			//累计位移
			sum: {
				//竖向位移
				z: {
					//累计变化范围
					data: "-1.1~1.0",
					//最大值出现位置
					location: "K126+378.95",
				},
				x: {
					//累计变化范围
					data: "-0.4~0.7",
					//最大值出现位置
					location: "K126+444.35",
				},
				y: {
					//累计变化范围
					data: "-0.6~0.6",
					//最大值出现位置
					location: "K126+346.25",
				},
			},
		},
		{
			//桥梁段
			name: "K131+776.17~K132+070.47",
			//日位移
			day: {
				//竖向位移
				z: {
					//变化范围
					data: "-0.3~0.0",
					//最大值出现位置
					location: "K131+972.37",
				},
				x: {
					//变化范围
					data: "-1.0~0.1",
					//最大值出现位置
					location: "K131+972.37",
				},
				y: {
					//变化范围
					data: "0.0~0.3",
					//最大值出现位置
					location: "K131+972.37",
				},
			},
			//累计位移
			sum: {
				//竖向位移
				z: {
					//累计变化范围
					data: "-0.3~0.1",
					//最大值出现位置
					location: "K131+906.97",
				},
				x: {
					//累计变化范围
					data: "-0.7~0.1",
					//最大值出现位置
					location: "K131+972.37",
				},
				y: {
					//累计变化范围
					data: "-0.4~0.2",
					//最大值出现位置
					location: "K132+070.47",
				},
			},
		},
	]);
</script>

<template>
	<el-table
		:data="dataList"
		style="width: 1200px"
		:header-cell-style="{ 'text-align': 'center' }"
		:cell-style="{ 'text-align': 'center' }"
	>
		<el-table-column :label="data + '数据简析:'" align="left">
			<el-table-column label="桥梁段" prop="name"></el-table-column>
			<el-table-column label="日位移" width="150">
				<el-table-column label="竖向位移" align="center">
					<el-table-column label="变形范围(mm)" prop="day.z.data" />
					<el-table-column label="最大值出现位置" prop="day.z.location" />
				</el-table-column>
				<el-table-column label="水平位移(纵桥向)">
					<el-table-column label="变形范围(mm)" prop="day.x.data" />
					<el-table-column label="最大值出现位置" prop="day.x.location" />
				</el-table-column>
				<el-table-column label="水平位移(横桥向)">
					<el-table-column label="变形范围(mm)" prop="day.y.data" />
					<el-table-column label="最大值出现位置" prop="day.y.location" />
				</el-table-column>
			</el-table-column>
			<el-table-column label="累计位移" width="150">
				<el-table-column label="竖向位移">
					<el-table-column label="变形范围(mm)" prop="sum.z.data" />
					<el-table-column label="最大值出现位置" prop="sum.z.location" />
				</el-table-column>
				<el-table-column label="水平位移(纵桥向)">
					<el-table-column label="变形范围(mm)" prop="sum.x.data" />
					<el-table-column label="最大值出现位置" prop="sum.x.location" />
				</el-table-column>
				<el-table-column label="水平位移(横桥向)">
					<el-table-column label="变形范围(mm)" prop="sum.y.data" />
					<el-table-column label="最大值出现位置" prop="sum.y.location" width="130" />
				</el-table-column>
			</el-table-column>
		</el-table-column>
	</el-table>
</template>

<style>
	.table {
		text-align: center;
	}
</style>
