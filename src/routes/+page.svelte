<script>
	import Nested from '../components/Nested.svelte';
	let name = 'Radnoumane';
	let src = 'https://picsum.photos/200/200';
	let stringWithHtml = `this is a <u>paragraph</u> with somes <b>html</b> tags decoded with <i>@html</i>`;
	let count = 0;
	function increment() {
		count += 1;
	}

	function reset() {
		count = 0;
	}

	$: doubled = count * 2 ;

	$: {
		console.log(`the count is ${count}`);
		console.log(`the count doubled is ${doubled}`)
	}
	$: if (count > 10){
		alert('count is dangerously high, reset init');
		count = 0;
	}

</script>

<h1>Welcome to Svelte tuto</h1>

<h3>hello {name.toUpperCase()}</h3>

<img {src} alt="a Random picture" />

<h4>this is a styled paragraph</h4>
<p>{@html stringWithHtml}</p>

<Nested />

<h2>Reactivity</h2>
<h3>Assignments</h3>
<button on:click={increment}> Increment </button>
<p> count clicked
	{count}
	{count === 1 ? 'time' : 'times'}
</p>
<button on:click={reset}> reset count </button>
<h3>Declarations</h3>
<p>{count} doubled is {doubled} </p>

<style>
	h4 {
		color: chocolate;
		font-family: 'Arial Narrow';
		font-size: 1.3em;
	}
</style>
