<script lang="ts">
	const phoneInternational = '519664761447';
	const phoneDisplay = '+51 966 476 1447';

	let nombre = '';
	let mensaje = '';

	$: waText = encodeURIComponent(
		`Hola, soy ${nombre || '...'}.\n\n${mensaje || 'Quiero una cotización para instalación de porcelanato/cerámicas.'}`
	);

	$: waLink = `https://wa.me/${phoneInternational}?text=${waText}`;
</script>

<section class="grid gap-4 md:grid-cols-2">
	<div class="rounded-3xl border border-white/10 bg-white/5 p-8">
		<h1 class="text-4xl font-black">Contacto</h1>

		<p class="mt-3 text-slate-300">
			Escríbeme por WhatsApp y dime ubicación + metros cuadrados para cotizar rápido.
		</p>

		<div class="mt-6 rounded-3xl border border-white/10 bg-slate-950/30 p-6">
			<p class="text-sm text-slate-300">Tel / WhatsApp</p>
			<p class="mt-1 text-2xl font-extrabold text-orange-400">{phoneDisplay}</p>

			<div class="mt-4 flex flex-wrap gap-3">
				<a
					href={waLink}
					target="_blank"
					rel="noreferrer"
					class="rounded-2xl bg-orange-500 px-6 py-3 font-bold text-slate-950 hover:bg-orange-400 transition"
				>
					Abrir WhatsApp
				</a>

				<a
					href="tel:+519664761447"
					class="rounded-2xl border border-white/10 bg-white/5 px-6 py-3 font-semibold hover:bg-white/10 transition"
				>
					Llamar
				</a>
			</div>
		</div>
	</div>

	<div class="rounded-3xl border border-white/10 bg-white/5 p-8">
		<h2 class="text-2xl font-extrabold">Enviar mensaje</h2>

		<label class="mt-5 block">
			<span class="text-sm text-slate-300">Tu nombre</span>
			<input
				bind:value={nombre}
				placeholder="Ej: Juan Pérez"
				class="mt-2 w-full rounded-2xl border border-white/10 bg-slate-950/30 px-4 py-3 outline-none focus:border-orange-400/60"
			/>
		</label>

		<label class="mt-4 block">
			<span class="text-sm text-slate-300">Mensaje</span>
			<textarea
				bind:value={mensaje}
				rows="6"
				placeholder="Ej: Baño 12 m², en (distrito/ciudad). Quiero porcelanato en paredes y piso."
				class="mt-2 w-full rounded-2xl border border-white/10 bg-slate-950/30 px-4 py-3 outline-none focus:border-orange-400/60"
			/>
		</label>

		<a
			href={waLink}
			target="_blank"
			rel="noreferrer"
			class="mt-5 block rounded-2xl bg-orange-500 px-6 py-3 text-center font-bold text-slate-950 hover:bg-orange-400 transition"
		>
			Enviar por WhatsApp
		</a>

		<p class="mt-3 text-sm text-slate-400">
			Consejo: agrega fotos del área para una mejor cotización.
		</p>
	</div>
</section>
