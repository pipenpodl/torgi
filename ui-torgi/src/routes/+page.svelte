<script>
	const products = [
		{
			id: 1,
			title: 'Беспроводные наушники Pro',
			price: '12 990 ₽',
			category: 'Аудио'
		},
		{
			id: 2,
			title: 'Умные часы FitPulse',
			price: '8 490 ₽',
			category: 'Гаджеты'
		},
		{
			id: 3,
			title: 'Портативная колонка Wave',
			price: '4 990 ₽',
			category: 'Акустика'
		}
	];
</script>

<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6 space-y-12">
	<!-- 1. Отдельный блок для фото (Баннер) -->
	<section class="w-full">
		<div class="relative w-full h-[340px] sm:h-[420px] md:h-[480px] rounded-2xl bg-stone-200 border-2 border-dashed border-stone-300 flex flex-col items-center justify-center overflow-hidden group">
			<!-- Плейсхолдер под фото -->
			<div class="text-center p-6 space-y-3">
				<div class="w-16 h-16 mx-auto rounded-full bg-stone-300/80 flex items-center justify-center text-stone-500 group-hover:bg-orange-500 group-hover:text-white transition">
					<svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z" />
					</svg>
				</div>
				<div>
					<h3 class="text-lg font-bold text-stone-700">Место для главного баннера / фото</h3>
					<p class="text-xs text-stone-500 mt-1">Здесь будет фоновое изображение или слайдер акций</p>
				</div>
			</div>

			<!-- Когда будет готова картинка, замените содержимое div на:
			<img src="/banner.jpg" alt="Главный баннер" class="w-full h-full object-cover" />
			-->
		</div>
	</section>

	<!-- 2. Секция с 3 карточками -->
	<section class="space-y-6">
		<div class="flex items-center justify-between border-b border-stone-200 pb-3">
			<h2 class="text-xl sm:text-2xl font-bold text-stone-900 tracking-tight">Популярные товары</h2>
			<a href="/catalog" class="text-sm font-semibold text-orange-500 hover:text-orange-600 transition">
				Все товары →
			</a>
		</div>

		<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
			{#each products as item}
				<div class="bg-white rounded-xl border border-stone-200 overflow-hidden shadow-sm hover:shadow-md transition flex flex-col group">
					<!-- Фото товара -->
					<div class="aspect-square bg-stone-100 border-b border-stone-100 flex flex-col items-center justify-center text-stone-400 group-hover:bg-stone-50 transition">
						<svg xmlns="http://www.w3.org/2000/svg" class="w-10 h-10 text-stone-300" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4" />
						</svg>
						<span class="text-xs mt-2 font-medium">Фото товара</span>
					</div>

					<!-- Описание -->
					<div class="p-4 flex-1 flex flex-col justify-between">
						<div>
							<span class="text-[11px] font-semibold text-orange-500 uppercase tracking-wider">{item.category}</span>
							<h3 class="text-base font-bold text-stone-900 mt-1 line-clamp-1 group-hover:text-orange-600 transition">
								{item.title}
							</h3>
						</div>

						<div class="mt-4 flex items-center justify-between pt-2">
							<span class="text-lg font-black text-stone-900">{item.price}</span>
							<button class="px-3.5 py-1.5 rounded-lg text-xs font-semibold bg-stone-900 text-white hover:bg-orange-500 active:scale-95 transition">
								В корзину
							</button>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</section>
</div>