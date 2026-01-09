<script lang="ts">
	import '../app.css';

	const phoneInternational = '526647614470';
	const waLink = `https://wa.me/${phoneInternational}?text=${encodeURIComponent(
		'Hola! Quiero una cotización para instalación de porcelanato/cerámicas.'
	)}`;

	const nav = [
		{ href: '/', label: 'Inicio' },
		{ href: '/quienes-somos', label: 'Quiénes somos' },
		{ href: '/servicios', label: 'Servicios' },
		{ href: '/contacto', label: 'Contacto' }
	];
</script>

<div class="min-h-screen bg-slate-950 text-slate-100">
	<header class="sticky top-0 z-50 border-b border-white/10 bg-slate-950/80 backdrop-blur">
		<div class="mx-auto flex max-w-6xl items-center justify-between gap-4 px-4 py-3">
			<a href="/" class="flex items-center gap-3">
				<img
					src="/INSTALACIONES.jpg"
					alt="Instalaciones Donaldo"
					class="h-12 w-12 rounded-xl object-cover border border-white/10"
				/>
				<div class="leading-tight">
					<div class="text-lg font-extrabold">Instalaciones Donaldo</div>
					<div class="text-xs text-slate-300">Porcelanato • Cerámicas • Loceta</div>
				</div>
			</a>

			<nav class="hidden items-center gap-2 md:flex">
				{#each nav as item}
					<a
						href={item.href}
						class="rounded-xl border border-white/10 bg-white/5 px-4 py-2 text-sm hover:bg-white/10 transition"
					>
						{item.label}
					</a>
				{/each}
			</nav>

			<a
				class="hidden rounded-xl bg-orange-500 px-4 py-2 text-sm font-bold text-slate-950 hover:bg-orange-400 transition md:inline-block"
				href={waLink}
				target="_blank"
				rel="noreferrer"
			>
				Cotizar por WhatsApp
			</a>
		</div>

		<!-- Menú móvil -->
		<div class="md:hidden border-t border-white/10">
			<div class="mx-auto grid max-w-6xl grid-cols-2 gap-2 px-4 py-3">
				{#each nav as item}
					<a
						href={item.href}
						class="rounded-xl border border-white/10 bg-white/5 px-3 py-2 text-center text-sm hover:bg-white/10 transition"
					>
						{item.label}
					</a>
				{/each}
			</div>
		</div>
	</header>

	<main class="mx-auto max-w-6xl px-4 py-8">
		<slot />
	</main>

	<footer class="border-t border-white/10">
		<div class="mx-auto max-w-6xl px-4 py-8 text-sm text-slate-300">
			<div class="flex flex-col gap-2 md:flex-row md:items-center md:justify-between">
				<span>© {new Date().getFullYear()} Instalaciones Donaldo</span>
				<span>
					WhatsApp:
					<a class="text-orange-400 hover:underline" href={waLink} target="_blank" rel="noreferrer">
						+52 6647614470
					</a>
				</span>
			</div>
		</div>
	</footer>

	<!-- Botón flotante WhatsApp -->
	<a
		href={waLink}
		target="_blank"
		rel="noreferrer"
		class="fixed bottom-5 right-5 grid h-14 w-14 place-items-center rounded-full bg-orange-500 text-slate-950 shadow-lg shadow-orange-500/20 hover:bg-orange-400 transition"
		aria-label="WhatsApp"
		title="WhatsApp"
	>
		<svg width="26" height="26" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true">
			<path
				d="M20.52 3.48A11.91 11.91 0 0 0 12.02 0C5.4 0 .02 5.38.02 12c0 2.12.55 4.2 1.6 6.03L0 24l6.16-1.6A11.96 11.96 0 0 0 12.02 24C18.64 24 24 18.62 24 12a11.9 11.9 0 0 0-3.48-8.52ZM12.02 22a9.98 9.98 0 0 1-5.1-1.4l-.37-.22-3.65.95.97-3.56-.24-.37A9.98 9.98 0 1 1 22 12c0 5.51-4.47 10-9.98 10Zm5.78-7.44c-.32-.16-1.9-.94-2.19-1.05-.29-.11-.5-.16-.71.16-.21.32-.82 1.05-1 1.27-.18.21-.37.24-.69.08-.32-.16-1.33-.49-2.53-1.56-.94-.84-1.58-1.88-1.77-2.2-.18-.32-.02-.49.14-.65.15-.15.32-.37.48-.55.16-.18.21-.32.32-.53.11-.21.05-.4-.03-.56-.08-.16-.71-1.71-.97-2.34-.26-.62-.53-.54-.71-.55h-.61c-.21 0-.56.08-.85.4-.29.32-1.12 1.09-1.12 2.66 0 1.56 1.15 3.08 1.31 3.29.16.21 2.26 3.45 5.48 4.83.77.33 1.37.52 1.84.67.77.24 1.47.2 2.02.12.62-.09 1.9-.78 2.17-1.53.27-.75.27-1.39.19-1.53-.08-.14-.29-.22-.61-.38Z"
			/>
		</svg>
	</a>
</div>
