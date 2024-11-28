<script>
	let { children } = $props();
</script>

<nav>
	<a href="/">Home</a>
	<a href="/add">Add Task</a>
</nav>

{@render children()}