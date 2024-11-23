<script>
	import "../app.css";
	import { contacts } from "../lib/contacts";
</script>

<div>
	<div class="min-h-80">
		<slot />
	</div>

	<footer
		class="footer bg-neutral text-neutral-content items-center p-4 flex flex-col md:flex-row md:justify-between"
	>
		<aside class="grid-flow-col items-center">
			<div>
				<p>Rino Vago</p>
				<p>Copyright © {new Date().getFullYear()} - All right reserved</p>
			</div>
		</aside>
		<nav class="grid-flow-col gap-6 md:place-self-center md:justify-self-end">
			{#each contacts as c}
				<a href={c.url} target="_blank">
					<img
						src="/img/{c.icon}.webp"
						alt="{c.title} icon"
						width="33"
						class="invert"
					/>
				</a>
			{/each}
		</nav>
	</footer>
</div>
