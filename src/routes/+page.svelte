<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import Tabs from './shared/Tabs.svelte';
	import Button from "./Button.svelte";
	import { InlineNotification } from "carbon-components-svelte";
	import { Link } from "carbon-components-svelte";
	import { TextArea } from "carbon-components-svelte";
	import { TextInput } from "carbon-components-svelte";
	import { Tag } from "carbon-components-svelte";
	
	// tabs
	let items = ['Tab 1', 'Tab 2'];
	let activeItem = 'Tab 1';
	const tabChange = (e) => {
		activeItem = e.detail;
	}

	//name
	let name = 'Katie';
	let nameColour = 'Blue';

	//button
	const handleClick = () => {
		nameColour = 'Orange';
	};

	const handleInput = (e) => {
		nameColour = e.target.value
	};
</script>

<main>
<!--INTRO-->

	<h1>Hello {name}!</h1>
	<p>{nameColour} is my favourite colour</p>
	<button on:click={handleClick}>Update to Orange</button>
	<!--<input type ="text" on:input={handleInput} ONE WAY DATA BINDING
		<input type ="text" on:input={handleInput} value={nameColour}> TWO WAY DATA BINDING-->
	<input type="text" bind:value={nameColour}> <!-- SHORTCUT TWO WAY DATA BINDING-->

<!--Text Area-->
<TextArea labelText="App description" placeholder="Enter a description..." />

<!--Text Input-->
<TextInput labelText="User name" placeholder="Enter user name..." />

<!--TABS-->

	<Tabs {activeItem} {items} on:tabChange={tabChange}/>
	{#if activeItem === 'Tab 1'} 
	<p>Text Goes Here</p>
	{:else if activeItem === 'Tab 2'}
	<p>Other Text Goes Here</p>
	{/if}

<!--BUTTON-->

	<Button class="primary sm">
		Good Button
	</Button>

	<Button class="danger lg" on:click={()=>console.log("Clicked")}>
		PANIC BUTTON
		</Button>


<!--InLine Notification-->

<InlineNotification
  title="Error:"
  subtitle="An internal server error occurred."
/>

<!-- Link -->
<Link href="https://www.diversetalent.ai/">DiverseTalent.ai</Link>

<!--Tag-->
<Tag>This is a Tag</Tag>


</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 400px;
		margin: 0 auto;
	}

	h1 {
		color: black;
		text-transform: upercase;
		font-size: 4em;
		font-weight: 100;
	}

	p {
		color: blue;
	}

</style>


<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>