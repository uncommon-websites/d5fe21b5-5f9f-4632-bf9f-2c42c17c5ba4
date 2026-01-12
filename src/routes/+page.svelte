<script lang="ts">
	// Icons
	const icons = {
		logo: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-500"><path d="M12 2L14.5 9H22L16 13.5L18.5 21L12 16.5L5.5 21L8 13.5L2 9H9.5L12 2Z" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg>`, // Placeholder for flower
		clock: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
		arrowRight: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>`,
		reflection: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
		productivity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`,
		memory: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/><path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/></svg>`,
		clarity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 2v4"/><path d="M12 18v4"/><path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/><path d="M2 12h4"/><path d="M18 12h4"/><path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/></svg>`,
		speedometer: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M22 12A10 10 0 0 0 12 2v10z"/></svg>`, // Simplified
		shield: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`,
		sparkles: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>`,
		soundwave: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 2v20"/><path d="M16 6v12"/><path d="M20 10v4"/><path d="M8 6v12"/><path d="M4 10v4"/></svg>`,
		plus: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>`,
		check: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="20 6 9 17 4 12"/></svg>`,
		calendar: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
		repeat: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>`,
		search: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>`,
		camera: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>`,
		mic: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
		download: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`,
		layout: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
		target: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`,
		list: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>`,
		link: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>`,
		maximize: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>`,
		externalLink: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>`,
	};
</script>

<div class="min-h-screen bg-gradient-to-br from-gray-50 via-primary-50/20 to-secondary-50/30 relative overflow-hidden">
	<!-- Atmospheric background elements -->
	<div class="absolute inset-0 opacity-30 pointer-events-none">
		<div class="absolute top-0 right-0 w-[600px] h-[600px] bg-gradient-radial from-primary-200/40 to-transparent rounded-full blur-3xl"></div>
		<div class="absolute bottom-0 left-0 w-[500px] h-[500px] bg-gradient-radial from-secondary-200/30 to-transparent rounded-full blur-3xl"></div>
	</div>
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-6 max-w-7xl mx-auto relative z-10 animate-fade-in">
		<div class="flex items-center gap-3">
			<!-- Logo Icon -->
			<div class="text-primary-600">
				<svg width="28" height="20" viewBox="0 0 117 78" fill="none" xmlns="http://www.w3.org/2000/svg">
					<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0101 48.3334H67.6809C65.1171 48.3334 62.6584 49.3518 60.8454 51.1647L56.8415 55.1687C55.0285 56.9817 52.5698 58 50.0059 58H34.6768C26.6686 58 20.1768 51.5081 20.1768 43.5C20.1768 35.4919 26.6686 29 34.6768 29H50.0059C52.5698 29 55.0285 27.9817 56.8415 26.1687L60.8454 22.1647C62.6584 20.3518 65.1171 19.3334 67.6809 19.3334H83.0101C91.0182 19.3334 97.5101 25.8253 97.5101 33.8334C97.5101 41.8415 91.0182 48.3334 83.0101 48.3334Z" fill="currentColor"/>
					<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0104 67.6667H67.6813C65.1174 67.6667 62.6587 68.6851 60.8457 70.498L56.8418 74.502C55.0288 76.3149 52.5701 77.3333 50.0062 77.3333H34.6771C15.9914 77.3333 0.84375 62.1857 0.84375 43.5C0.84375 24.8143 15.9914 9.66667 34.6771 9.66667H50.0062C52.5701 9.66667 55.0288 8.64828 56.8418 6.8353L60.8457 2.83129C62.6587 1.01846 65.1174 0 67.6813 0H83.0104C101.696 0 116.844 15.1477 116.844 33.8333C116.844 52.519 101.696 67.6667 83.0104 67.6667ZM67.6813 9.66667C65.1174 9.66667 62.6587 10.6851 60.8457 12.498L56.8418 16.502C55.0288 18.3149 52.5701 19.3333 50.0062 19.3333H34.6771C21.3302 19.3333 10.5104 30.1532 10.5104 43.5C10.5104 56.8468 21.3302 67.6667 34.6771 67.6667H50.0062C52.5701 67.6667 55.0288 66.6483 56.8418 64.8353L60.8457 60.8314C62.6587 59.0184 65.1174 58 67.6813 58H83.0104C96.3572 58 107.177 47.1801 107.177 33.8333C107.177 20.4866 96.3572 9.66667 83.0104 9.66667H67.6813Z" fill="currentColor"/>
				</svg>
			</div>
			<span class="font-display font-bold text-2xl tracking-tight text-gray-900">Socrates</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#" class="text-gray-700 hover:text-primary-600 transition-colors">Features</a>
			<a href="#" class="bg-primary-600 px-5 py-2.5 rounded-full text-white hover:bg-primary-700 transition-all hover:scale-105">Get Started</a>
		</nav>
	</header>

	<main class="relative z-10">
		<!-- Hero Section -->
		<section class="max-w-5xl mx-auto px-6 pt-16 pb-24 text-center relative">
			<div class="inline-flex items-center gap-2 text-primary-700 text-sm mb-8 animate-fade-in" style="animation-delay: 0.1s; opacity: 0;">
				{@html icons.sparkles}
				<span class="font-medium">Elegant reading for focused minds</span>
			</div>
			
			<h1 class="font-display text-6xl md:text-7xl lg:text-8xl font-bold text-gray-900 mb-8 leading-[1.05] tracking-tight animate-fade-in-up" style="animation-delay: 0.2s; opacity: 0;">
				Transform scattered reading into <span class="text-primary-600 italic">focused knowledge</span>
			</h1>
			
			<p class="text-xl md:text-2xl text-gray-700 mb-12 max-w-3xl mx-auto leading-relaxed animate-fade-in" style="animation-delay: 0.4s; opacity: 0;">
				Socrates turns the chaos of tabs and bookmarks into a beautifully curated reading experience. Save, read, and retain what matters.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-xl mx-auto mb-20 animate-scale-in" style="animation-delay: 0.6s; opacity: 0;">
				<div class="relative w-full group">
					<input 
						type="email" 
						placeholder="Your email address" 
						class="w-full pl-5 pr-14 py-4 rounded-2xl border-2 border-gray-300 bg-white/80 backdrop-blur-sm focus:outline-none focus:ring-2 focus:ring-primary-500/30 focus:border-primary-500 transition-all text-base group-hover:border-primary-400"
					/>
					<button class="absolute right-3 top-1/2 -translate-y-1/2 p-2 bg-primary-600 text-white rounded-xl hover:bg-primary-700 transition-all hover:scale-110">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-sm text-gray-600 w-full sm:w-auto shrink-0 font-medium">
					Join the waitlist for<br>early access
				</div>
			</div>

			<!-- Hero Image -->
			<div class="relative rounded-3xl border-4 border-primary-200/50 overflow-hidden aspect-[16/10] mb-16 animate-scale-in" style="animation-delay: 0.8s; opacity: 0; box-shadow: 0 25px 50px -12px rgba(212, 106, 56, 0.25);">
				<img 
					src="/generated/image-a-professional-knowledge-worker-at-a-mod-1765583620920-0.webp" 
					alt="Professional using Socrates for focused reading" 
					class="w-full h-full object-cover"
				/>
				
				<!-- Floating UI Elements -->
				<!-- Save Article Card - Top Left -->
				<div class="absolute top-6 left-6 bg-white/95 backdrop-blur-sm rounded-xl border border-gray-200 p-4 shadow-lg max-w-[280px] hidden md:block">
					<div class="flex items-start gap-3">
						<div class="w-10 h-10 bg-primary-100 rounded-lg flex items-center justify-center shrink-0">
							{@html icons.link}
						</div>
						<div class="flex-1 min-w-0">
							<div class="text-xs font-bold text-gray-900 mb-1">Article saved</div>
							<div class="text-xs text-gray-600 truncate">The Future of Knowledge Work</div>
							<div class="flex gap-2 mt-2">
								<span class="text-xs bg-primary-100 text-primary-700 px-2 py-0.5 rounded">Design</span>
								<span class="text-xs bg-gray-100 text-gray-700 px-2 py-0.5 rounded">Research</span>
							</div>
						</div>
					</div>
				</div>

				<!-- Reading Progress - Bottom Right -->
				<div class="absolute bottom-6 right-6 bg-white/95 backdrop-blur-sm rounded-xl border border-gray-200 p-4 shadow-lg hidden md:block">
					<div class="flex items-center gap-3">
						<div class="w-12 h-12 rounded-full border-4 border-primary-500 border-t-transparent animate-spin" style="animation-duration: 3s;"></div>
						<div>
							<div class="text-xs font-bold text-gray-900">Reading progress</div>
							<div class="text-xs text-gray-600">67% complete · 4 min left</div>
						</div>
					</div>
				</div>

				<!-- Keyboard Shortcut Hint - Top Right -->
				<div class="absolute top-6 right-6 bg-gray-900/90 backdrop-blur-sm rounded-lg px-3 py-2 shadow-lg hidden lg:block">
					<div class="flex items-center gap-2 text-white text-xs">
						<kbd class="bg-white/20 px-2 py-1 rounded text-xs font-mono">⌘</kbd>
						<kbd class="bg-white/20 px-2 py-1 rounded text-xs font-mono">S</kbd>
						<span class="text-gray-300">to save</span>
					</div>
				</div>
			</div>

			<!-- Bottom Icons -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-14 text-base font-medium text-gray-800 animate-fade-in" style="animation-delay: 1s; opacity: 0;">
				<div class="flex items-center gap-2.5 group cursor-pointer">
					<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.reflection}</div>
					<span class="group-hover:text-primary-700 transition-colors">Deep reading</span>
				</div>
				<div class="flex items-center gap-2.5 group cursor-pointer">
					<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.list}</div>
					<span class="group-hover:text-primary-700 transition-colors">Smart curation</span>
				</div>
				<div class="flex items-center gap-2.5 group cursor-pointer">
					<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.memory}</div>
					<span class="group-hover:text-primary-700 transition-colors">Knowledge retention</span>
				</div>
				<div class="flex items-center gap-2.5 group cursor-pointer">
					<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.clarity}</div>
					<span class="group-hover:text-primary-700 transition-colors">Focus & clarity</span>
				</div>
			</div>
		</section>

		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-24 relative">
			<!-- Decorative element -->
			<div class="absolute top-0 left-1/2 -translate-x-1/2 w-px h-20 bg-gradient-to-b from-transparent via-primary-300 to-transparent"></div>
			
			<h2 class="font-display text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-16 max-w-2xl leading-tight">
				Reading reimagined for the way you <span class="text-primary-600 italic">think</span>
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gradient-to-br from-primary-50 to-primary-100/50 p-8 rounded-3xl flex flex-col items-start h-72 relative overflow-hidden border border-primary-200/50 group hover:scale-[1.02] transition-all duration-300 cursor-pointer">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-primary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<div class="mb-auto text-primary-700 relative z-10 group-hover:scale-110 transition-transform">
						{@html icons.sparkles}
					</div>
					<div class="relative z-10">
						<h3 class="font-display font-bold text-xl mb-3 text-gray-900">Elegant design</h3>
						<p class="text-sm text-gray-700 leading-relaxed">A beautifully minimal interface that feels premium and stays out of your way</p>
					</div>
					<!-- Typography Controls Overlay -->
					<div class="absolute top-4 right-4 bg-white/90 backdrop-blur-sm rounded-xl border border-primary-200 p-2.5 shadow-lg z-10 group-hover:scale-105 transition-transform">
						<div class="flex gap-1.5">
							<button class="w-7 h-7 flex items-center justify-center text-xs font-display font-bold text-gray-400 hover:text-primary-700 transition-colors">A</button>
							<button class="w-7 h-7 flex items-center justify-center text-sm font-display font-bold text-primary-700">A</button>
							<button class="w-7 h-7 flex items-center justify-center text-base font-display font-bold text-gray-400 hover:text-primary-700 transition-colors">A</button>
						</div>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gradient-to-br from-secondary-50 to-secondary-100/50 p-8 rounded-3xl flex flex-col items-start h-72 relative overflow-hidden border border-secondary-200/50 group hover:scale-[1.02] transition-all duration-300 cursor-pointer">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-secondary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<div class="mb-auto text-secondary-700 relative z-10 group-hover:scale-110 transition-transform">
						{@html icons.maximize}
					</div>
					<div class="relative z-10">
						<h3 class="font-display font-bold text-xl mb-3 text-gray-900">Distraction-free</h3>
						<p class="text-sm text-gray-700 leading-relaxed">Clean reading experience without ads, popups, or clutter</p>
					</div>
					<!-- Focus Mode Indicator -->
					<div class="absolute top-4 right-4 bg-secondary-600 text-white rounded-full px-4 py-2 text-xs font-bold shadow-lg z-10 animate-pulse-glow group-hover:scale-105 transition-transform">
						Focus mode
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gradient-to-br from-gray-100 to-gray-200/50 p-8 rounded-3xl flex flex-col items-start h-72 relative overflow-hidden border border-gray-300/50 group hover:scale-[1.02] transition-all duration-300 cursor-pointer">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-gray-300/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<div class="mb-auto text-gray-800 relative z-10 group-hover:scale-110 transition-transform">
						{@html icons.speedometer}
					</div>
					<div class="relative z-10">
						<h3 class="font-display font-bold text-xl mb-3 text-gray-900">Lightning fast</h3>
						<p class="text-sm text-gray-700 leading-relaxed">Native apps for mobile and desktop that work seamlessly offline</p>
					</div>
					<!-- Offline Indicator -->
					<div class="absolute bottom-4 right-4 flex items-center gap-2 bg-white/90 backdrop-blur-sm rounded-xl border border-gray-300 px-4 py-2 shadow-lg z-10 group-hover:scale-105 transition-transform">
						<div class="w-2.5 h-2.5 bg-green-500 rounded-full animate-pulse"></div>
						<span class="text-xs font-bold text-gray-800">Offline ready</span>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gradient-to-br from-primary-50 to-primary-100/50 p-8 rounded-3xl flex flex-col items-start h-72 relative overflow-hidden border border-primary-200/50 group hover:scale-[1.02] transition-all duration-300 cursor-pointer">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-primary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<div class="mb-auto text-primary-700 relative z-10 group-hover:scale-110 transition-transform">
						{@html icons.list}
					</div>
					<div class="relative z-10">
						<h3 class="font-display font-bold text-xl mb-3 text-gray-900">Smart curation</h3>
						<p class="text-sm text-gray-700 leading-relaxed">Organize articles with tags, collections, and powerful search</p>
					</div>
					<!-- Tag Selector -->
					<div class="absolute top-4 right-4 flex flex-wrap gap-1.5 max-w-[130px] z-10">
						<span class="text-xs bg-white/90 backdrop-blur-sm border border-primary-200 text-primary-800 px-3 py-1 rounded-full font-medium shadow-sm group-hover:scale-105 transition-transform">Design</span>
						<span class="text-xs bg-white/90 backdrop-blur-sm border border-primary-200 text-primary-800 px-3 py-1 rounded-full font-medium shadow-sm group-hover:scale-105 transition-transform">Tech</span>
						<span class="text-xs bg-primary-600 text-white px-3 py-1 rounded-full font-bold shadow-sm group-hover:scale-105 transition-transform">+3</span>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gradient-to-br from-secondary-50 to-secondary-100/50 p-8 rounded-3xl flex flex-col items-start h-72 relative overflow-hidden border border-secondary-200/50 group hover:scale-[1.02] transition-all duration-300 cursor-pointer">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-secondary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<div class="mb-auto text-secondary-700 relative z-10 group-hover:scale-110 transition-transform">
						{@html icons.link}
					</div>
					<div class="relative z-10">
						<h3 class="font-display font-bold text-xl mb-3 text-gray-900">Save anything</h3>
						<p class="text-sm text-gray-700 leading-relaxed">One-click saving from any browser or app with our extensions</p>
					</div>
					<!-- Browser Extension Badge -->
					<div class="absolute top-4 right-4 bg-white/90 backdrop-blur-sm rounded-xl border border-secondary-200 p-2.5 shadow-lg z-10 group-hover:scale-105 transition-transform">
						<div class="flex items-center gap-2">
							<div class="w-5 h-5 bg-secondary-600 rounded-md"></div>
							<span class="text-xs font-bold text-gray-800">Chrome</span>
						</div>
					</div>
				</div>

				<!-- Card 6 -->
				<div class="bg-gradient-to-br from-gray-100 to-gray-200/50 p-8 rounded-3xl flex flex-col items-start h-72 relative overflow-hidden border border-gray-300/50 group hover:scale-[1.02] transition-all duration-300 cursor-pointer">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-gray-300/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<div class="mb-auto text-gray-800 relative z-10 group-hover:scale-110 transition-transform">
						{@html icons.shield}
					</div>
					<div class="relative z-10">
						<h3 class="font-display font-bold text-xl mb-3 text-gray-900">Always synced</h3>
						<p class="text-sm text-gray-700 leading-relaxed">Your reading list stays in sync across all your devices</p>
					</div>
					<!-- Sync Status -->
					<div class="absolute top-4 right-4 flex flex-col gap-1.5 z-10">
						<div class="flex items-center gap-2 bg-white/90 backdrop-blur-sm rounded-lg border border-gray-300 px-3 py-1.5 shadow-sm group-hover:scale-105 transition-transform">
							<div class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></div>
							<span class="text-xs font-bold text-gray-800">Mac</span>
						</div>
						<div class="flex items-center gap-2 bg-white/90 backdrop-blur-sm rounded-lg border border-gray-300 px-3 py-1.5 shadow-sm group-hover:scale-105 transition-transform">
							<div class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></div>
							<span class="text-xs font-bold text-gray-800">iPhone</span>
						</div>
					</div>
				</div>
			</div>
		</section>

		<!-- Reading Experience Section -->
		<section class="max-w-6xl mx-auto px-6 py-24 relative">
			<!-- Decorative gradient blob -->
			<div class="absolute -top-40 -right-40 w-96 h-96 bg-gradient-radial from-secondary-200/40 to-transparent rounded-full blur-3xl pointer-events-none"></div>
			
			<div class="mb-16 relative z-10">
				<span class="inline-block bg-gradient-to-r from-primary-600 to-primary-700 text-white px-4 py-2 rounded-full text-xs font-bold uppercase tracking-wider mb-8 shadow-lg">
					Reading Experience
				</span>
				<h2 class="font-display text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-8 tracking-tight leading-tight">
					Built for <span class="text-secondary-600 italic">deep reading</span>
				</h2>
				<p class="text-xl md:text-2xl text-gray-700 max-w-2xl leading-relaxed">
					Every detail designed to help you focus on what matters—the content. No distractions, just pure reading.
				</p>
			</div>

			<div class="bg-gradient-to-br from-primary-50 via-secondary-50/30 to-primary-50 rounded-[2.5rem] p-8 md:p-12 mb-16 border-2 border-primary-200/50 relative overflow-hidden">
				<!-- Decorative pattern overlay -->
				<div class="absolute inset-0 opacity-5" style="background-image: radial-gradient(circle at 2px 2px, currentColor 1px, transparent 0); background-size: 32px 32px;"></div>
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
					<!-- Left Visual: Mobile Reading -->
					<div class="relative bg-white rounded-2xl shadow-lg overflow-hidden min-h-[300px]">
						<img 
							src="/generated/image-close-up-of-hands-holding-a-smartphone-d-1765583623714-1.webp" 
							alt="Elegant mobile reading interface" 
							class="w-full h-full object-cover"
						/>
						<!-- Reading Controls Overlay -->
						<div class="absolute bottom-4 left-4 right-4 bg-white/95 backdrop-blur-sm rounded-xl border border-gray-200 p-3 shadow-lg">
							<div class="flex items-center justify-between mb-2">
								<span class="text-xs font-medium text-gray-600">Reading time: 8 min</span>
								<div class="flex gap-2">
									<button class="w-7 h-7 flex items-center justify-center bg-gray-100 rounded-lg text-gray-600 hover:bg-gray-200">
										{@html icons.reflection}
									</button>
									<button class="w-7 h-7 flex items-center justify-center bg-primary-100 rounded-lg text-primary-600">
										{@html icons.sparkles}
									</button>
								</div>
							</div>
							<div class="w-full bg-gray-200 rounded-full h-1.5">
								<div class="bg-primary-500 h-1.5 rounded-full" style="width: 45%"></div>
							</div>
						</div>
					</div>

					<!-- Right Visual: Desktop Reading -->
					<div class="relative bg-white rounded-2xl shadow-lg overflow-hidden min-h-[300px]">
						<img 
							src="/generated/image-a-curated-collection-of-articles-display-1765583625976-2.webp" 
							alt="Organized article collection" 
							class="w-full h-full object-cover"
						/>
						<!-- Highlight Tool Overlay -->
						<div class="absolute top-4 left-1/2 -translate-x-1/2 bg-gray-900/95 backdrop-blur-sm rounded-xl border border-gray-700 px-4 py-2 shadow-lg">
							<div class="flex items-center gap-3">
								<button class="w-8 h-8 flex items-center justify-center bg-yellow-400 rounded-lg text-gray-900 hover:bg-yellow-300">
									<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="w-4 h-4">
										<path d="M12 20h9"/>
										<path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/>
									</svg>
								</button>
								<button class="w-8 h-8 flex items-center justify-center text-white hover:bg-white/10 rounded-lg">
									{@html icons.reflection}
								</button>
								<button class="w-8 h-8 flex items-center justify-center text-white hover:bg-white/10 rounded-lg">
									{@html icons.link}
								</button>
							</div>
						</div>
					</div>
				</div>

				<!-- Bottom Visual: Save & Organize -->
				<div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
					<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
						<div class="text-center">
							<div class="w-12 h-12 bg-primary-100 rounded-full flex items-center justify-center mx-auto mb-3">
								{@html icons.link}
							</div>
							<h5 class="font-bold text-gray-900 mb-2">Save from anywhere</h5>
							<p class="text-xs text-gray-600">Browser extensions, mobile share sheet, or email forwarding</p>
						</div>
						<div class="text-center">
							<div class="w-12 h-12 bg-primary-100 rounded-full flex items-center justify-center mx-auto mb-3">
								{@html icons.list}
							</div>
							<h5 class="font-bold text-gray-900 mb-2">Auto-organize</h5>
							<p class="text-xs text-gray-600">Smart collections and tags keep everything organized automatically</p>
						</div>
						<div class="text-center">
							<div class="w-12 h-12 bg-primary-100 rounded-full flex items-center justify-center mx-auto mb-3">
								{@html icons.search}
							</div>
							<h5 class="font-bold text-gray-900 mb-2">Find instantly</h5>
							<p class="text-xs text-gray-600">Powerful full-text search across all your saved articles</p>
						</div>
					</div>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-4 max-w-4xl">
				<p class="text-xl text-gray-600 mb-6 md:col-span-2 leading-relaxed">
					Socrates removes friction from your reading workflow, so you can focus on learning and retaining what matters.
				</p>
				
				<div class="space-y-4">
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.maximize}
						<span>Distraction-free reader</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.reflection}
						<span>Highlight & annotate</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.speedometer}
						<span>Offline reading</span>
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.list}
						<span>Smart collections</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.search}
						<span>Full-text search</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.shield}
						<span>Cross-device sync</span>
					</div>
				</div>
			</div>
		</section>

		<!-- Curation Section -->
		<section class="max-w-6xl mx-auto px-6 py-24 relative">
			<!-- Decorative gradient blob -->
			<div class="absolute -top-40 -left-40 w-96 h-96 bg-gradient-radial from-primary-200/40 to-transparent rounded-full blur-3xl pointer-events-none"></div>
			
			<div class="mb-16 relative z-10">
				<span class="inline-block bg-gray-900 text-white px-4 py-2 rounded-full text-xs font-bold uppercase tracking-wider mb-8 shadow-lg">
					Organization
				</span>
				<h2 class="font-display text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-8 tracking-tight leading-tight">
					Your personal <span class="text-primary-600 italic">knowledge library</span>
				</h2>
				<p class="text-xl md:text-2xl text-gray-700 max-w-2xl leading-relaxed">
					Organize articles into collections, tag for easy discovery, and build a searchable archive of everything you've read.
				</p>
			</div>

			<div class="bg-gradient-to-br from-gray-100 via-gray-50 to-primary-50/30 rounded-[2.5rem] p-8 md:p-12 mb-16 relative border-2 border-gray-300/50 overflow-hidden">
				<!-- Decorative pattern overlay -->
				<div class="absolute inset-0 opacity-5" style="background-image: radial-gradient(circle at 2px 2px, currentColor 1px, transparent 0); background-size: 32px 32px;"></div>
				<!-- Floating Tag Pills -->
				<div class="absolute top-4 right-4 hidden lg:flex flex-wrap gap-2 max-w-[200px]">
					<span class="text-xs bg-white border border-gray-200 text-gray-700 px-3 py-1 rounded-full shadow-sm">Product</span>
					<span class="text-xs bg-white border border-gray-200 text-gray-700 px-3 py-1 rounded-full shadow-sm">Design</span>
					<span class="text-xs bg-white border border-gray-200 text-gray-700 px-3 py-1 rounded-full shadow-sm">Strategy</span>
					<span class="text-xs bg-white border border-gray-200 text-gray-700 px-3 py-1 rounded-full shadow-sm">Research</span>
				</div>
				
				<div class="bg-white rounded-2xl shadow-sm p-6 md:p-8 max-w-3xl mx-auto relative">
					<!-- Search Bar Overlay -->
					<div class="absolute -top-4 left-1/2 -translate-x-1/2 w-[90%] max-w-md bg-white rounded-xl border border-gray-200 shadow-lg p-3 hidden md:block">
						<div class="flex items-center gap-2">
							<div class="text-gray-400">
								{@html icons.search}
							</div>
							<input 
								type="text" 
								placeholder="Search articles, tags, collections..." 
								class="flex-1 text-sm text-gray-600 outline-none bg-transparent"
								disabled
							/>
							<kbd class="bg-gray-100 px-2 py-1 rounded text-xs font-mono text-gray-500">⌘K</kbd>
						</div>
					</div>
					
					<!-- Stats -->
					<div class="grid grid-cols-4 gap-4 mb-8 mt-8 md:mt-0">
						<div class="bg-primary-100 p-3 rounded-xl relative">
							<div class="text-xs font-bold text-primary-800 mb-1">Unread</div>
							<div class="text-2xl font-bold text-primary-900">47</div>
							<div class="absolute -top-1 -right-1 w-3 h-3 bg-primary-500 rounded-full border-2 border-white"></div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Reading</div>
							<div class="text-2xl font-bold text-gray-900">3</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Archived</div>
							<div class="text-2xl font-bold text-gray-900">284</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Favorites</div>
							<div class="text-2xl font-bold text-gray-900">18</div>
						</div>
					</div>

					<!-- Collections List -->
					<div class="space-y-6">
						<div>
							<div class="text-xs font-bold text-primary-600 mb-3 tracking-wide">COLLECTIONS</div>
							<div class="space-y-3">
								<div class="flex gap-4 items-center p-3 rounded-lg hover:bg-gray-50 cursor-pointer">
									<div class="w-10 h-10 rounded-lg bg-primary-100 flex items-center justify-center">
										<span class="text-lg">📚</span>
									</div>
									<div class="flex-1">
										<h4 class="font-bold text-gray-900">Product Design</h4>
										<p class="text-xs text-gray-500">24 articles</p>
									</div>
								</div>
								<div class="flex gap-4 items-center p-3 rounded-lg hover:bg-gray-50 cursor-pointer">
									<div class="w-10 h-10 rounded-lg bg-gray-100 flex items-center justify-center">
										<span class="text-lg">💼</span>
									</div>
									<div class="flex-1">
										<h4 class="font-bold text-gray-900">Startup Strategy</h4>
										<p class="text-xs text-gray-500">18 articles</p>
									</div>
								</div>
								<div class="flex gap-4 items-center p-3 rounded-lg hover:bg-gray-50 cursor-pointer">
									<div class="w-10 h-10 rounded-lg bg-gray-100 flex items-center justify-center">
										<span class="text-lg">🧠</span>
									</div>
									<div class="flex-1">
										<h4 class="font-bold text-gray-900">Psychology & Behavior</h4>
										<p class="text-xs text-gray-500">31 articles</p>
									</div>
								</div>
								<div class="flex gap-4 items-center p-3 rounded-lg hover:bg-gray-50 cursor-pointer">
									<div class="w-10 h-10 rounded-lg bg-gray-100 flex items-center justify-center">
										<span class="text-lg">⚡</span>
									</div>
									<div class="flex-1">
										<h4 class="font-bold text-gray-900">Technology Trends</h4>
										<p class="text-xs text-gray-500">42 articles</p>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row gap-8 md:items-start justify-between">
				<div class="flex gap-6 text-sm font-medium text-gray-600">
					<div class="flex items-center gap-2">
						{@html icons.list}
						<span>Collections</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.target}
						<span>Tags</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.search}
						<span>Search</span>
					</div>
				</div>
				<p class="text-xl text-gray-600 max-w-lg leading-relaxed">
					Build a personal knowledge base that grows with you. Every article saved, organized, and ready when you need it.
				</p>
			</div>
		</section>

		<!-- Who uses it Section -->
		<section class="max-w-7xl mx-auto px-6 py-24 relative">
			<!-- Decorative gradient blob -->
			<div class="absolute top-0 right-0 w-96 h-96 bg-gradient-radial from-secondary-200/30 to-transparent rounded-full blur-3xl pointer-events-none"></div>
			
			<div class="mb-16 relative z-10">
				<span class="inline-block bg-gradient-to-r from-gray-800 to-gray-900 text-white px-4 py-2 rounded-full text-xs font-bold uppercase tracking-wider mb-8 shadow-lg">
					Use cases
				</span>
				<h2 class="font-display text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-8 tracking-tight leading-tight">
					Perfect for <span class="text-secondary-600 italic">knowledge workers</span>
				</h2>
				<p class="text-xl md:text-2xl text-gray-700 max-w-3xl leading-relaxed">
					Socrates helps professionals stay on top of their reading without the chaos of scattered tabs and bookmarks.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-5 relative z-10">
				<!-- Card 1 -->
				<div class="bg-gradient-to-br from-primary-100 to-primary-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-primary-200/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-primary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Industry research</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Stay current with trends and insights in your field without drowning in tabs.</p>
					<!-- Mini Article Card -->
					<div class="absolute top-2 right-2 w-16 h-20 bg-white rounded-lg border border-gray-200 shadow-sm p-2">
						<div class="w-full h-8 bg-gray-200 rounded mb-1"></div>
						<div class="w-full h-1 bg-gray-200 rounded mb-0.5"></div>
						<div class="w-3/4 h-1 bg-gray-200 rounded"></div>
					</div>
				</div>
				<!-- Card 2 -->
				<div class="bg-gradient-to-br from-secondary-100 to-secondary-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-secondary-200/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-secondary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Competitive analysis</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Collect and organize articles about competitors and market movements.</p>
					<!-- Collection Badge -->
					<div class="absolute top-2 right-2 bg-white rounded-lg border border-gray-200 px-2 py-1 shadow-sm">
						<div class="text-xs font-medium text-gray-700">📊 Analysis</div>
					</div>
				</div>
				<!-- Card 3 -->
				<div class="bg-gradient-to-br from-gray-100 to-gray-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-gray-300/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-gray-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Learning & development</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Build a curated library of resources for skill development and growth.</p>
					<!-- Progress Indicator -->
					<div class="absolute top-3 right-3 flex flex-col gap-1.5 z-10">
						<div class="w-14 h-1.5 bg-primary-600 rounded-full"></div>
						<div class="w-14 h-1.5 bg-primary-400 rounded-full"></div>
						<div class="w-14 h-1.5 bg-gray-300 rounded-full"></div>
					</div>
				</div>
				<!-- Card 4 -->
				<div class="bg-gradient-to-br from-primary-100 to-primary-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-primary-200/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-primary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Content inspiration</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Save examples and ideas that inspire your own writing and creation.</p>
					<!-- Bookmark Icon -->
					<div class="absolute top-3 right-3 w-7 h-9 bg-primary-600 rounded-b-sm z-10 shadow-lg" style="clip-path: polygon(0 0, 100% 0, 100% 100%, 50% 75%, 0 100%)"></div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gradient-to-br from-secondary-100 to-secondary-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-secondary-200/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-secondary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Product research</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Gather insights about user needs, design patterns, and best practices.</p>
					<!-- Stacked Cards -->
					<div class="absolute top-3 right-3 z-10">
						<div class="w-14 h-16 bg-white/90 backdrop-blur-sm rounded-lg border border-secondary-300 shadow-md absolute top-0 right-0"></div>
						<div class="w-14 h-16 bg-white/90 backdrop-blur-sm rounded-lg border border-secondary-300 shadow-md absolute top-1 right-1"></div>
						<div class="w-14 h-16 bg-white/90 backdrop-blur-sm rounded-lg border border-secondary-300 shadow-md absolute top-2 right-2"></div>
					</div>
				</div>
				<!-- Card 6 -->
				<div class="bg-gradient-to-br from-gray-100 to-gray-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-gray-300/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-gray-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Investment research</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Track market analysis, company profiles, and financial insights.</p>
					<!-- Chart Icon -->
					<div class="absolute top-3 right-3 w-12 h-12 bg-white/90 backdrop-blur-sm rounded-xl border border-gray-300 shadow-lg p-2 z-10">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="w-full h-full text-green-600">
							<polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/>
						</svg>
					</div>
				</div>
				<!-- Card 7 -->
				<div class="bg-gradient-to-br from-primary-100 to-primary-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-primary-200/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-primary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Academic reading</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Organize papers, articles, and research materials for your studies.</p>
					<!-- Citation Badge -->
					<div class="absolute top-3 right-3 bg-white/90 backdrop-blur-sm rounded-lg border border-primary-300 px-3 py-1.5 shadow-lg z-10">
						<div class="text-sm font-mono font-bold text-primary-800">[1]</div>
					</div>
				</div>
				<!-- Card 8 -->
				<div class="bg-gradient-to-br from-secondary-100 to-secondary-50 p-6 rounded-2xl min-h-[220px] flex flex-col relative overflow-hidden border border-secondary-200/50 hover:scale-[1.03] transition-all duration-300 cursor-pointer group">
					<div class="absolute inset-0 bg-gradient-to-br from-transparent to-secondary-200/20 opacity-0 group-hover:opacity-100 transition-opacity"></div>
					<h3 class="font-display font-bold text-lg text-gray-900 mb-2 relative z-10">Newsletter curation</h3>
					<p class="text-sm text-gray-700 mt-auto leading-relaxed relative z-10">Save the best articles from your favorite newsletters in one place.</p>
					<!-- Email Icon -->
					<div class="absolute top-3 right-3 w-11 h-9 bg-white/90 backdrop-blur-sm rounded-lg border border-secondary-300 shadow-lg flex items-center justify-center z-10">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="w-5 h-5 text-secondary-700">
							<path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
							<polyline points="22,6 12,13 2,6"/>
						</svg>
					</div>
				</div>
			</div>
		</section>

		<!-- Final CTA Section -->
		<section class="max-w-6xl mx-auto px-6 py-24 relative">
			<!-- Decorative gradient blobs -->
			<div class="absolute -bottom-40 -left-40 w-96 h-96 bg-gradient-radial from-primary-300/30 to-transparent rounded-full blur-3xl pointer-events-none"></div>
			<div class="absolute -bottom-40 -right-40 w-96 h-96 bg-gradient-radial from-secondary-300/30 to-transparent rounded-full blur-3xl pointer-events-none"></div>
			
			<div class="bg-gradient-to-br from-gray-950 via-gray-900 to-gray-950 rounded-[2.5rem] overflow-hidden relative border-4 border-primary-600/20 shadow-2xl" style="box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5), 0 0 80px rgba(212, 106, 56, 0.15);">
				<!-- Animated gradient overlay -->
				<div class="absolute inset-0 bg-gradient-to-br from-primary-600/10 via-transparent to-secondary-600/10 opacity-50"></div>
				<!-- Floating Stats Badge -->
				<div class="absolute top-6 left-6 bg-white/10 backdrop-blur-sm rounded-xl border border-white/20 px-4 py-3 shadow-lg hidden lg:block z-10">
					<div class="flex items-center gap-3">
						<div class="flex -space-x-2">
							<div class="w-8 h-8 rounded-full bg-primary-400 border-2 border-gray-950"></div>
							<div class="w-8 h-8 rounded-full bg-primary-500 border-2 border-gray-950"></div>
							<div class="w-8 h-8 rounded-full bg-primary-600 border-2 border-gray-950"></div>
						</div>
						<div>
							<div class="text-xs font-bold text-white">2,847 readers</div>
							<div class="text-xs text-gray-400">joined this week</div>
						</div>
					</div>
				</div>
				
				<div class="grid grid-cols-1 md:grid-cols-2">
					<div class="p-10 md:p-14 flex flex-col justify-center relative z-10">
						<h2 class="font-display text-4xl md:text-5xl lg:text-6xl font-bold text-white mb-8 leading-tight">
							Start reading with <span class="text-primary-400 italic">focus</span>
						</h2>
						<p class="text-xl text-gray-300 mb-10 leading-relaxed">
							Join design-conscious professionals who've transformed their reading habits with Socrates.
						</p>
						<div class="flex flex-col sm:flex-row gap-4">
							<input 
								type="email" 
								placeholder="Your email address" 
								class="flex-1 px-5 py-4 rounded-2xl border-2 border-gray-700 bg-gray-900/50 backdrop-blur-sm text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-primary-500/50 focus:border-primary-500 transition-all text-base"
							/>
							<button class="bg-gradient-to-r from-primary-600 to-primary-700 hover:from-primary-700 hover:to-primary-800 text-white font-bold px-8 py-4 rounded-2xl transition-all hover:scale-105 shadow-lg">
								Get Started
							</button>
						</div>
						<p class="text-sm text-gray-400 mt-5 font-medium">Free 14-day trial. No credit card required.</p>
						
						<!-- Feature Pills -->
						<div class="flex flex-wrap gap-3 mt-8">
							<div class="flex items-center gap-2 bg-white/10 backdrop-blur-sm rounded-full px-4 py-2 border border-white/20 hover:bg-white/15 transition-colors">
								<div class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></div>
								<span class="text-sm text-gray-200 font-medium">No credit card</span>
							</div>
							<div class="flex items-center gap-2 bg-white/10 backdrop-blur-sm rounded-full px-4 py-2 border border-white/20 hover:bg-white/15 transition-colors">
								<div class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></div>
								<span class="text-sm text-gray-200 font-medium">Cancel anytime</span>
							</div>
							<div class="flex items-center gap-2 bg-white/10 backdrop-blur-sm rounded-full px-4 py-2 border border-white/20 hover:bg-white/15 transition-colors">
								<div class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></div>
								<span class="text-sm text-gray-200 font-medium">14-day trial</span>
							</div>
						</div>
					</div>
					<div class="hidden md:block relative">
						<img 
							src="/generated/image-a-young-professional-commuting-on-public-1765583628400-3.webp" 
							alt="Professional reading on mobile" 
							class="w-full h-full object-cover"
						/>
						<!-- Mobile App Preview Badge -->
						<div class="absolute bottom-6 right-6 bg-white/95 backdrop-blur-sm rounded-xl border border-gray-200 p-3 shadow-lg">
							<div class="flex items-center gap-2">
								<div class="w-10 h-10 bg-gray-900 rounded-xl flex items-center justify-center">
									<svg width="20" height="14" viewBox="0 0 117 78" fill="white" xmlns="http://www.w3.org/2000/svg">
										<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0101 48.3334H67.6809C65.1171 48.3334 62.6584 49.3518 60.8454 51.1647L56.8415 55.1687C55.0285 56.9817 52.5698 58 50.0059 58H34.6768C26.6686 58 20.1768 51.5081 20.1768 43.5C20.1768 35.4919 26.6686 29 34.6768 29H50.0059C52.5698 29 55.0285 27.9817 56.8415 26.1687L60.8454 22.1647C62.6584 20.3518 65.1171 19.3334 67.6809 19.3334H83.0101C91.0182 19.3334 97.5101 25.8253 97.5101 33.8334C97.5101 41.8415 91.0182 48.3334 83.0101 48.3334Z" fill="white"/>
									</svg>
								</div>
								<div>
									<div class="text-xs font-bold text-gray-900">Socrates</div>
									<div class="text-xs text-gray-600">Available on iOS</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-16 border-t-2 border-primary-200/30 relative">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-10">
				<div>
					<h4 class="font-display font-bold text-base text-gray-900 mb-5">Resources</h4>
					<div class="grid grid-cols-2 gap-x-10 gap-y-4 text-sm text-gray-700">
						<a href="#" class="flex items-center gap-2.5 hover:text-primary-600 transition-colors group">
							<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.reflection}</div> Reading guide
						</a>
						<a href="#" class="flex items-center gap-2.5 hover:text-primary-600 transition-colors group">
							<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.plus}</div> Getting started
						</a>
						<a href="#" class="flex items-center gap-2.5 hover:text-primary-600 transition-colors group">
							<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.download}</div> Browser extensions
						</a>
						<a href="#" class="flex items-center gap-2.5 hover:text-primary-600 transition-colors group">
							<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.list}</div> Organizing tips
						</a>
						<a href="#" class="flex items-center gap-2.5 hover:text-primary-600 transition-colors group">
							<div class="text-primary-600 group-hover:scale-110 transition-transform">{@html icons.sparkles}</div> Feature updates
						</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center mt-16 pt-10 text-sm text-gray-500 border-t border-gray-200">
				<div class="flex items-center gap-3 mb-6 md:mb-0">
					<div class="w-7 h-7 text-primary-600">
						<svg width="28" height="20" viewBox="0 0 117 78" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
							<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0101 48.3334H67.6809C65.1171 48.3334 62.6584 49.3518 60.8454 51.1647L56.8415 55.1687C55.0285 56.9817 52.5698 58 50.0059 58H34.6768C26.6686 58 20.1768 51.5081 20.1768 43.5C20.1768 35.4919 26.6686 29 34.6768 29H50.0059C52.5698 29 55.0285 27.9817 56.8415 26.1687L60.8454 22.1647C62.6584 20.3518 65.1171 19.3334 67.6809 19.3334H83.0101C91.0182 19.3334 97.5101 25.8253 97.5101 33.8334C97.5101 41.8415 91.0182 48.3334 83.0101 48.3334ZM67.6809 29C65.1171 29 62.6584 30.0184 60.8454 31.8314L56.8415 35.8353C55.0285 37.6483 52.5698 38.6667 50.0059 38.6667H34.6768C32.0073 38.6667 29.8434 40.8306 29.8434 43.5C29.8434 46.1695 32.0073 48.3334 34.6768 48.3334H50.0059C52.5698 48.3334 55.0285 47.315 56.8415 45.502L60.8454 41.4981C62.6584 39.6851 65.1171 38.6667 67.6809 38.6667H83.0101C85.6795 38.6667 87.8434 36.5028 87.8434 33.8334C87.8434 31.1639 85.6795 29 83.0101 29H67.6809Z" fill="currentColor"/>
							<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0104 67.6667H67.6813C65.1174 67.6667 62.6587 68.6851 60.8457 70.498L56.8418 74.502C55.0288 76.3149 52.5701 77.3333 50.0062 77.3333H34.6771C15.9914 77.3333 0.84375 62.1857 0.84375 43.5C0.84375 24.8143 15.9914 9.66667 34.6771 9.66667H50.0062C52.5701 9.66667 55.0288 8.64828 56.8418 6.8353L60.8457 2.83129C62.6587 1.01846 65.1174 0 67.6813 0H83.0104C101.696 0 116.844 15.1477 116.844 33.8333C116.844 52.519 101.696 67.6667 83.0104 67.6667ZM67.6813 9.66667C65.1174 9.66667 62.6587 10.6851 60.8457 12.498L56.8418 16.502C55.0288 18.3149 52.5701 19.3333 50.0062 19.3333H34.6771C21.3302 19.3333 10.5104 30.1532 10.5104 43.5C10.5104 56.8468 21.3302 67.6667 34.6771 67.6667H50.0062C52.5701 67.6667 55.0288 66.6483 56.8418 64.8353L60.8457 60.8314C62.6587 59.0184 65.1174 58 67.6813 58H83.0104C96.3572 58 107.177 47.1801 107.177 33.8333C107.177 20.4866 96.3572 9.66667 83.0104 9.66667H67.6813Z" fill="currentColor"/>
						</svg>
					</div>
					<div class="font-medium">
						<p class="text-gray-700">Copyright © 2025 Socrates</p>
						<p class="text-gray-500 text-xs mt-0.5">All rights reserved. Terms of Service & Privacy Policy.</p>
					</div>
				</div>
				<div class="bg-green-100 text-green-700 px-4 py-2 rounded-full text-xs font-bold flex items-center gap-2">
					<div class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></div>
					All systems operational
				</div>
			</div>
		</footer>

	</main>
</div>

