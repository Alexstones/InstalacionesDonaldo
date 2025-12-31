<script lang="ts">
	const servicios = [
		{
			titulo: 'Instalación de porcelanato',
			desc: 'Pisos y paredes, formatos grandes, alineación, nivelación y cortes precisos.'
		},
		{
			titulo: 'Instalación de cerámicas',
			desc: 'Baños, cocinas y zonas húmedas con juntas prolijas y buen acabado.'
		},
		{
			titulo: 'Loceta y enchapes',
			desc: 'Revestimientos, guardas, esquinas, terminaciones y remates.'
		},
		{
			titulo: 'Escaleras',
			desc: 'Medición, cortes a detalle, acabado seguro y bien alineado.'
		},
		{
			titulo: 'Pisos (interior y exterior)',
			desc: 'Colocación de piezas, nivelación, pendientes y terminaciones limpias.'
		},
		{
			titulo: 'Reparaciones y cambios',
			desc: 'Reemplazo de piezas, corrección de juntas, resanes y ajustes.'
		}
	];

	const phoneInternational = '526647614470';
	const waLink = `https://wa.me/${phoneInternational}?text=${encodeURIComponent(
		'Hola! Quiero una cotización de servicios de porcelanato y cerámicas.'
	)}`;
</script>

<section class="rounded-3xl border border-white/10 bg-white/5 p-8">
	<h1 class="text-4xl font-black">Servicios</h1>

	<p class="mt-3 max-w-3xl text-slate-300">
		Servicio profesional de <strong>loceta</strong>, <strong>porcelanato</strong> y
		<strong>cerámicas</strong> en <strong>baños</strong>, <strong>cocinas</strong>,
		<strong>escaleras</strong> y <strong>pisos</strong>.
	</p>

	<div class="mt-8 grid gap-4 md:grid-cols-3">
		{#each servicios as s}
			<div class="rounded-3xl border border-white/10 bg-slate-950/30 p-6 hover:bg-slate-950/40 transition">
				<h2 class="text-xl font-extrabold">{s.titulo}</h2>
				<p class="mt-2 text-slate-300">{s.desc}</p>
			</div>
		{/each}
	</div>

	<div class="mt-8 flex flex-wrap gap-3">
		<a
			href={waLink}
			target="_blank"
			rel="noreferrer"
			class="rounded-2xl bg-orange-500 px-6 py-3 font-bold text-slate-950 hover:bg-orange-400 transition"
		>
			Cotizar por WhatsApp
		</a>

		<a
			href="/contacto"
			class="rounded-2xl border border-white/10 bg-white/5 px-6 py-3 font-semibold hover:bg-white/10 transition"
		>
			Ir a Contacto
		</a>
	</div>
</section>
