<script>
	import BarChart from './BarChart.svelte';
	import Login from './Login.svelte';
	import TvChart from './TVChart.svelte';
	var data = [30, 86, 133, 81, 303, 365];
	let count = 0;
	let symbol='NVDA';
	$: doubled = data;

	const sayHi = () => {
		for(let i=0; i < doubled.length - 1; i++){
			doubled[i]*=2
			console.log(doubled)
		}
	};

</script>

<style>
</style>

<h1>Hello</h1>
<p> This is a paragraph. </p>
<button on:click={sayHi}>Click to Double</button>
<p>{count} * 2 = {doubled}</p>

<input bind:value={symbol}>

<p>The best stonk is {symbol}</p>

<Login />
<BarChart data={doubled}/>
<p>{doubled}</p>

<BarChart data={[1,2,3,22,3,1]} />

<TvChart />

