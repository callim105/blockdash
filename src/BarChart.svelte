<script>
	import { afterUpdate, beforeUpdate, onMount } from 'svelte';
	import * as d3 from 'd3';
    export let data;
	
    $: db = data;
	let el;

	onMount(() => {
		d3.select(el)
			.selectAll("div")
			.data(db)
			.enter()
			.append("div")
			.style("width", function(d) {
				return d + "px";
			})
			.text(function(d) {
				return d;
			});
	});

    const updateChart = () => {
		d3.selectAll("div")
          .data(data)
          .enter()
          .append("div")
          .style("width", function(d) {
				return d + "px";
		  })
		  .text(function(d) {
				return d;
		  });

	}


</script>

<style>
	.chart :global(div) {
		font: 10px sans-serif;
		background-color: steelblue;
		text-align: right;
		padding: 3px;
		margin: 1px;
		color: white;
	}
</style>

<h1>Bar Chart</h1>
<button id="myButton">Update</button>
<p>{data}</p>
<div bind:this={el} class="chart"></div>