<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import { Tabs, Tab, TabContent } from "carbon-components-svelte";
	import { Button } from "carbon-components-svelte";
	import { InlineNotification } from "carbon-components-svelte";
	import { Link } from "carbon-components-svelte";
	import { TextArea } from "carbon-components-svelte";
	import { TextInput } from "carbon-components-svelte";
	import { Tag } from "carbon-components-svelte";


</script>

<main>

<!--TABS-->
	<Tabs>
		<Tab label="The Joke" />
		<Tab label="The Answer" />
		<Tab label="An Inspiring Quote" />
		<svelte:fragment slot="content">
		  <TabContent>Why don't dinosaurs talk? </TabContent>
		  <TabContent> Because they're dead.</TabContent>
		  <TabContent>Whatever you do, always give 100%. Unless you're donating blood.</TabContent>
		</svelte:fragment>
	  </Tabs>

<!--INTRO-->

<h1> Hello, Katie! </h1>
<p> Welcome to your first <strong>REAL</strong> svelte project</p>

<!--Text Area-->
<TextArea labelText="TEXTBOX" placeholder="You write whatever you feel is right..." />

<!--Text Input-->
<TextInput labelText="What's your name?" placeholder="Enter name please..." />



<!--BUTTON-->

<Button > We are a button
</Button>
<Button kind="danger">DANGEERRRR</Button>


<!--InLine Notification-->

<InlineNotification
  title="Oh dear:"
  subtitle="Seems to be a wee error here."
/>

<!-- Link -->
<Link href="https://www.diversetalent.ai/">Click here to access DiverseTalent.ai's website</Link>

<!--Tag-->
<Tag>Tag, you're it</Tag>


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
		color: black;
	}

</style>


<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>
