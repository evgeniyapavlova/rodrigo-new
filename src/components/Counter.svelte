<script>
	import '$lib/styles/counter.scss';

	let investment = 100;
	let operations = 10;

	const investmentLimit = 1000;
	const operationsLimit = 100;

	$: potentialEarnings = calculateEarnings(investment, operations);

	function calculateEarnings(investment, operations) {
		const efficiency = 1 + operations / 20;
		return Math.round(investment * efficiency * 3);
	}

	function updateRangeStyleById(id, value) {
		const input = document.getElementById(id);
		if (!input) return;

		const min = +input.min;
		const max = +input.max;
		const percent = ((+value - min) / (max - min)) * 100;

		document.getElementById(`${id}-wrap`)?.style.setProperty('--progress', `${percent}%`);
	}
</script>

<div class="counter-wrap">
	<div class="counter-title heading">Cuánto podrías ganar como miembro</div>
	<div class="counter">
		<div class="range-group">
			<label for="investment" class="heading">Cantidad de inversión</label>
			<div class="input-number-wrap">
				<div class="input-prefix">$</div>
				<input
					type="text"
					min="0"
					max={investmentLimit}
					inputmode="numeric"
					pattern="[0-9]*"
					bind:value={investment}
					on:input={(e) => {
						const raw = e.target.value;
						const cleaned = raw.replace(/[^0-9]/g, '');

						if (raw !== cleaned) {
							e.target.value = cleaned;
						}

						let value = cleaned === '' ? '' : +cleaned;

						if (value !== '' && value > investmentLimit) {
							value = investmentLimit;
							e.target.value = value;
						}

						investment = value;
						updateRangeStyleById('investment', investment || 0);
					}}
					class="number-input"
				/>
			</div>

			<div class="input-wrap" id="investment-wrap">
				<input
					id="investment"
					type="range"
					min="0"
					max={investmentLimit}
					step="1"
					value={investment || 0}
					on:input={(e) => {
						investment = +e.target.value;
						updateRangeStyleById('investment', investment);
					}}
				/>
			</div>

			<div class="counter-limits">
				<span>$0</span>
				<span>${investmentLimit}</span>
			</div>
		</div>

		<div class="range-group">
			<label for="operations" class="heading">Número de operaciones</label>
			<input
				type="text"
				min="0"
				max={operationsLimit}
				inputmode="numeric"
				pattern="[0-9]*"
				bind:value={operations}
				on:input={(e) => {
					const raw = e.target.value;
					const cleaned = raw.replace(/[^0-9]/g, '');

					if (raw !== cleaned) {
						e.target.value = cleaned;
					}

					let value = cleaned === '' ? '' : +cleaned;

					if (value !== '' && value > operationsLimit) {
						value = operationsLimit;
						e.target.value = value;
					}

					operations = value;
					updateRangeStyleById('operations', operations || 0);
				}}
				class="number-input"
			/>

			<div class="input-wrap" id="operations-wrap">
				<input
					id="operations"
					type="range"
					min="0"
					max={operationsLimit}
					step="1"
					value={operations || 0}
					on:input={(e) => {
						operations = +e.target.value;
						updateRangeStyleById('operations', operations);
					}}
				/>
			</div>

			<div class="counter-limits">
				<span>0</span>
				<span>{operationsLimit}</span>
			</div>
		</div>

		<div class="output">
			<div class="output-amount">
				${potentialEarnings.toLocaleString()}
			</div>
			<div class="output-text">Beneficio potencial</div>
		</div>
	</div>
	<div class="counter-footer">*Ejemplo de beneficio potencial</div>
</div>
