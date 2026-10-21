<script>
	import './layout.css';

	let { children } = $props(); // В Svelte 4 используйте: export let data;
</script>

<div class="flex min-h-screen flex-col bg-stone-100 font-sans text-stone-900 antialiased">
	<!-- Узкая фиксированная шапка (h-14 = 56px) -->
	<header
		class="fixed top-0 right-0 left-0 z-50 h-14 w-full border-b border-stone-200 bg-white/95 shadow-sm backdrop-blur-md"
	>
		<div class="mx-auto flex h-full max-w-7xl items-center justify-between px-4 sm:px-6 lg:px-8">
			<!-- Логотип -->
			<a href="/" class="flex items-center gap-2">
				<div
					class="flex h-7 w-7 items-center justify-center rounded-lg bg-orange-500 text-sm font-extrabold text-white shadow-sm"
				>
					O
				</div>
				<span class="text-lg font-bold tracking-tight text-stone-900">
					Orange<span class="text-orange-500">Shop</span>
				</span>
			</a>

			<!-- Навигация -->
			<nav class="hidden items-center gap-6 text-sm font-medium text-stone-600 md:flex">
				<a href="/" class="font-semibold text-orange-500 transition hover:text-orange-600"
					>Главная</a
				>
				<a href="/catalog" class="transition hover:text-orange-500">Каталог</a>
				<a href="/about" class="transition hover:text-orange-500">О нас</a>
				<a href="/contacts" class="transition hover:text-orange-500">Контакты</a>
			</nav>

			<!-- Правая часть: Корзина -->
			<div class="flex items-center gap-3">
				<button
					class="relative rounded-lg p-2 text-stone-700 transition hover:bg-stone-100"
					aria-label="Корзина"
				>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"
						></path>
					</svg>
					<span
						class="absolute top-1 right-1 flex h-3.5 w-3.5 items-center justify-center rounded-full bg-orange-500 text-[10px] font-bold text-white"
					>
						0
					</span>
				</button>
			</div>
		</div>
	</header>

	<!-- Отступ сверху pt-14 компенсирует высоту фиксированной шапки -->
	<main class="flex-1 pt-14">
		{@render children()}
	</main>

	<!-- Темный футер -->
	<footer class="border-t border-stone-800 bg-stone-900 text-stone-400">
		<div class="mx-auto max-w-7xl px-4 py-10 sm:px-6 lg:px-8">
			<div class="mb-8 grid grid-cols-1 gap-8 text-sm sm:grid-cols-2 md:grid-cols-4">
				<div>
					<div class="mb-3 flex items-center gap-2">
						<div
							class="flex h-6 w-6 items-center justify-center rounded bg-orange-500 text-xs font-bold text-white"
						>
							O
						</div>
						<span class="text-base font-bold text-white">OrangeShop</span>
					</div>
					<p class="text-xs text-stone-400">Качественные товары с оперативной доставкой.</p>
				</div>
				<div>
					<h4 class="mb-3 text-xs font-semibold tracking-wider text-white uppercase">Разделы</h4>
					<ul class="space-y-1.5 text-xs">
						<li><a href="/" class="transition hover:text-orange-400">Главная</a></li>
						<li><a href="/catalog" class="transition hover:text-orange-400">Каталог</a></li>
					</ul>
				</div>
				<div>
					<h4 class="mb-3 text-xs font-semibold tracking-wider text-white uppercase">Информация</h4>
					<ul class="space-y-1.5 text-xs">
						<li><a href="/about" class="transition hover:text-orange-400">О нас</a></li>
						<li><a href="/contacts" class="transition hover:text-orange-400">Контакты</a></li>
					</ul>
				</div>
				<div>
					<h4 class="mb-3 text-xs font-semibold tracking-wider text-white uppercase">Контакты</h4>
					<p class="text-xs text-stone-300">+7 (999) 000-00-00</p>
					<p class="mt-1 text-xs text-stone-400">support@orangeshop.com</p>
				</div>
			</div>
			<div class="border-t border-stone-800 pt-6 text-center text-xs text-stone-500 sm:text-left">
				© {new Date().getFullYear()} OrangeShop. Все права защищены.
			</div>
		</div>
	</footer>
</div>
