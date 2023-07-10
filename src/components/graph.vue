<script setup>
	import { ref, onMounted } from "vue";
	import * as echarts from "echarts";
	const grap = ref();
	onMounted(() => {
		let myChart = echarts.init(grap.value);
		let option = {
			title: {
				show: true,
				text: "桥梁段K126+248.15~K126+509.75 竖向位移累计分布图",
				x: "center",
			},
			xAxis: {
				type: "category",
				data: [
					"K126+248.15",
					"K126+280.85",
					"K126+313.55",
					"K126+346.25",
					"K126+378.95",
					"K126+411.65",
					"K126+444.35",
					"K126+477.05",
					"K126+509.75",
				],
				axisLabel: {
					rotate: 45, // 设置标签倾斜角度，单位为度
				},
			},
			tooltip: {
				show: true,
				trigger: "axis",
			},
			yAxis: {
				type: "value",
			},
			series: [
				{
					data: [1.0, -0.2, 0.7, -0.2, -1.1, -1.0, 0.1, 0.2, 0.3],
					type: "line",
					smooth: true,
				},
			],
		};

		myChart.setOption(option);
	});
</script>

<template>
	<div ref="grap" style="width: 1000px; height: 400px"></div>
</template>

<style></style>
