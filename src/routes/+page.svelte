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

<div class="min-h-screen bg-white">
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-4 max-w-7xl mx-auto">
		<div class="flex items-center gap-2">
			<!-- Logo Icon -->
			<div class="text-gray-900">
				<svg width="24" height="16" viewBox="0 0 117 78" fill="none" xmlns="http://www.w3.org/2000/svg">
					<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0101 48.3334H67.6809C65.1171 48.3334 62.6584 49.3518 60.8454 51.1647L56.8415 55.1687C55.0285 56.9817 52.5698 58 50.0059 58H34.6768C26.6686 58 20.1768 51.5081 20.1768 43.5C20.1768 35.4919 26.6686 29 34.6768 29H50.0059C52.5698 29 55.0285 27.9817 56.8415 26.1687L60.8454 22.1647C62.6584 20.3518 65.1171 19.3334 67.6809 19.3334H83.0101C91.0182 19.3334 97.5101 25.8253 97.5101 33.8334C97.5101 41.8415 91.0182 48.3334 83.0101 48.3334ZM67.6809 29C65.1171 29 62.6584 30.0184 60.8454 31.8314L56.8415 35.8353C55.0285 37.6483 52.5698 38.6667 50.0059 38.6667H34.6768C32.0073 38.6667 29.8434 40.8306 29.8434 43.5C29.8434 46.1695 32.0073 48.3334 34.6768 48.3334H50.0059C52.5698 48.3334 55.0285 47.315 56.8415 45.502L60.8454 41.4981C62.6584 39.6851 65.1171 38.6667 67.6809 38.6667H83.0101C85.6795 38.6667 87.8434 36.5028 87.8434 33.8334C87.8434 31.1639 85.6795 29 83.0101 29H67.6809Z" fill="currentColor"/>
					<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0104 67.6667H67.6813C65.1174 67.6667 62.6587 68.6851 60.8457 70.498L56.8418 74.502C55.0288 76.3149 52.5701 77.3333 50.0062 77.3333H34.6771C15.9914 77.3333 0.84375 62.1857 0.84375 43.5C0.84375 24.8143 15.9914 9.66667 34.6771 9.66667H50.0062C52.5701 9.66667 55.0288 8.64828 56.8418 6.8353L60.8457 2.83129C62.6587 1.01846 65.1174 0 67.6813 0H83.0104C101.696 0 116.844 15.1477 116.844 33.8333C116.844 52.519 101.696 67.6667 83.0104 67.6667ZM67.6813 9.66667C65.1174 9.66667 62.6587 10.6851 60.8457 12.498L56.8418 16.502C55.0288 18.3149 52.5701 19.3333 50.0062 19.3333H34.6771C21.3302 19.3333 10.5104 30.1532 10.5104 43.5C10.5104 56.8468 21.3302 67.6667 34.6771 67.6667H50.0062C52.5701 67.6667 55.0288 66.6483 56.8418 64.8353L60.8457 60.8314C62.6587 59.0184 65.1174 58 67.6813 58H83.0104C96.3572 58 107.177 47.1801 107.177 33.8333C107.177 20.4866 96.3572 9.66667 83.0104 9.66667H67.6813Z" fill="currentColor"/>
				</svg>
			</div>
			<span class="font-bold text-xl tracking-tight">Socrates</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#" class="text-gray-600 hover:text-gray-900">Features</a>
			<a href="#" class="bg-gray-100 px-4 py-2 rounded-lg text-gray-900 hover:bg-gray-200 transition-colors">Get Started</a>
		</nav>
	</header>

	<main>
		<!-- Hero Section -->
		<section class="max-w-4xl mx-auto px-6 pt-12 pb-20 text-center">
			<div class="inline-flex items-center gap-2 text-gray-500 text-sm mb-6">
				{@html icons.sparkles}
				<span>Elegant reading for focused minds</span>
			</div>
			
			<h1 class="text-5xl md:text-6xl font-bold tracking-tight text-gray-900 mb-6 leading-[1.1]">
				Transform scattered reading into focused knowledge
			</h1>
			
			<p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
				Socrates turns the chaos of tabs and bookmarks into a beautifully curated reading experience. Save, read, and retain what matters.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto mb-16">
				<div class="relative w-full">
					<input 
						type="email" 
						placeholder="Your email address" 
						class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary-500/20 focus:border-primary-500 transition-all"
					/>
					<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-gray-600">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-xs text-left text-gray-500 w-full sm:w-auto shrink-0">
					Join the waitlist for<br>early access
				</div>
			</div>

			<!-- Hero Image -->
			<div class="relative rounded-2xl border border-gray-200 shadow-2xl overflow-hidden aspect-[16/10] mb-12">
				<img 
					src="/generated/image-a-professional-knowledge-worker-at-a-mod-1765583620920-0.webp" 
					alt="Professional using Socrates for focused reading" 
					class="w-full h-full object-cover"
				/>
			</div>

			<!-- Bottom Icons -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-12 text-sm font-medium text-gray-700">
				<div class="flex items-center gap-2">
					{@html icons.reflection}
					<span>Deep reading</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.list}
					<span>Smart curation</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.memory}
					<span>Knowledge retention</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.clarity}
					<span>Focus & clarity</span>
				</div>
			</div>
		</section>

		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-lg leading-tight">
				Reading reimagined for the way you think
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.sparkles}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Elegant design</h3>
						<p class="text-sm text-gray-600 leading-relaxed">A beautifully minimal interface that feels premium and stays out of your way</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.maximize}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Distraction-free</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Clean reading experience without ads, popups, or clutter</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.speedometer}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Lightning fast</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Native apps for mobile and desktop that work seamlessly offline</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.list}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Smart curation</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Organize articles with tags, collections, and powerful search</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.link}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Save anything</h3>
						<p class="text-sm text-gray-600 leading-relaxed">One-click saving from any browser or app with our extensions</p>
					</div>
				</div>

				<!-- Card 6 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.shield}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Always synced</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Your reading list stays in sync across all your devices</p>
					</div>
				</div>
			</div>
		</section>

		<!-- Reading Experience Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-primary-100 text-primary-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Reading Experience
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Built for deep reading
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Every detail designed to help you focus on what matters—the content. No distractions, just pure reading.
				</p>
			</div>

			<div class="bg-primary-50/30 rounded-3xl p-8 md:p-12 mb-16">
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
					<!-- Left Visual: Mobile Reading -->
					<div class="relative bg-white rounded-2xl shadow-lg overflow-hidden min-h-[300px]">
						<img 
							src="/generated/image-close-up-of-hands-holding-a-smartphone-d-1765583623714-1.webp" 
							alt="Elegant mobile reading interface" 
							class="w-full h-full object-cover"
						/>
					</div>

					<!-- Right Visual: Desktop Reading -->
					<div class="relative bg-white rounded-2xl shadow-lg overflow-hidden min-h-[300px]">
						<img 
							src="/generated/image-a-curated-collection-of-articles-display-1765583625976-2.webp" 
							alt="Organized article collection" 
							class="w-full h-full object-cover"
						/>
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
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-900 text-white px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Organization
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Your personal knowledge library
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Organize articles into collections, tag for easy discovery, and build a searchable archive of everything you've read.
				</p>
			</div>

			<div class="bg-gray-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="bg-white rounded-2xl shadow-sm p-6 md:p-8 max-w-3xl mx-auto">
					<!-- Stats -->
					<div class="grid grid-cols-4 gap-4 mb-8">
						<div class="bg-primary-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-primary-800 mb-1">Unread</div>
							<div class="text-2xl font-bold text-primary-900">47</div>
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
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Use cases
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Perfect for knowledge workers
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Socrates helps professionals stay on top of their reading without the chaos of scattered tabs and bookmarks.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
				<!-- Card 1 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Industry research</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Stay current with trends and insights in your field without drowning in tabs.</p>
				</div>
				<!-- Card 2 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Competitive analysis</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Collect and organize articles about competitors and market movements.</p>
				</div>
				<!-- Card 3 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Learning & development</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Build a curated library of resources for skill development and growth.</p>
				</div>
				<!-- Card 4 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Content inspiration</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Save examples and ideas that inspire your own writing and creation.</p>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Product research</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Gather insights about user needs, design patterns, and best practices.</p>
				</div>
				<!-- Card 6 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Investment research</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Track market analysis, company profiles, and financial insights.</p>
				</div>
				<!-- Card 7 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Academic reading</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Organize papers, articles, and research materials for your studies.</p>
				</div>
				<!-- Card 8 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Newsletter curation</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Save the best articles from your favorite newsletters in one place.</p>
				</div>
			</div>
		</section>

		<!-- Final CTA Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="bg-gray-950 rounded-3xl overflow-hidden">
				<div class="grid grid-cols-1 md:grid-cols-2">
					<div class="p-8 md:p-12 flex flex-col justify-center">
						<h2 class="text-3xl md:text-4xl font-bold text-white mb-6">
							Start reading with focus
						</h2>
						<p class="text-lg text-gray-300 mb-8">
							Join design-conscious professionals who've transformed their reading habits with Socrates.
						</p>
						<div class="flex flex-col sm:flex-row gap-4">
							<input 
								type="email" 
								placeholder="Your email address" 
								class="flex-1 px-4 py-3 rounded-lg border border-gray-700 bg-gray-900 text-white placeholder-gray-500 focus:outline-none focus:ring-2 focus:ring-primary-500/50 focus:border-primary-500"
							/>
							<button class="bg-primary-500 hover:bg-primary-600 text-white font-medium px-6 py-3 rounded-lg transition-colors">
								Get Started
							</button>
						</div>
						<p class="text-xs text-gray-500 mt-4">Free 14-day trial. No credit card required.</p>
					</div>
					<div class="hidden md:block">
						<img 
							src="/generated/image-a-young-professional-commuting-on-public-1765583628400-3.webp" 
							alt="Professional reading on mobile" 
							class="w-full h-full object-cover"
						/>
					</div>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-12 border-t border-gray-100">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Resources</h4>
					<div class="grid grid-cols-2 gap-x-8 gap-y-3 text-xs text-gray-600">
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.reflection} Reading guide
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.plus} Getting started
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.download} Browser extensions
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.list} Organizing tips
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.sparkles} Feature updates
						</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center mt-12 pt-8 text-xs text-gray-400">
				<div class="flex items-center gap-2 mb-4 md:mb-0">
					<div class="w-6 h-6 text-gray-300">
						<svg width="24" height="16" viewBox="0 0 117 78" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
							<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0101 48.3334H67.6809C65.1171 48.3334 62.6584 49.3518 60.8454 51.1647L56.8415 55.1687C55.0285 56.9817 52.5698 58 50.0059 58H34.6768C26.6686 58 20.1768 51.5081 20.1768 43.5C20.1768 35.4919 26.6686 29 34.6768 29H50.0059C52.5698 29 55.0285 27.9817 56.8415 26.1687L60.8454 22.1647C62.6584 20.3518 65.1171 19.3334 67.6809 19.3334H83.0101C91.0182 19.3334 97.5101 25.8253 97.5101 33.8334C97.5101 41.8415 91.0182 48.3334 83.0101 48.3334ZM67.6809 29C65.1171 29 62.6584 30.0184 60.8454 31.8314L56.8415 35.8353C55.0285 37.6483 52.5698 38.6667 50.0059 38.6667H34.6768C32.0073 38.6667 29.8434 40.8306 29.8434 43.5C29.8434 46.1695 32.0073 48.3334 34.6768 48.3334H50.0059C52.5698 48.3334 55.0285 47.315 56.8415 45.502L60.8454 41.4981C62.6584 39.6851 65.1171 38.6667 67.6809 38.6667H83.0101C85.6795 38.6667 87.8434 36.5028 87.8434 33.8334C87.8434 31.1639 85.6795 29 83.0101 29H67.6809Z" fill="currentColor"/>
							<path fill-rule="evenodd" clip-rule="evenodd" d="M83.0104 67.6667H67.6813C65.1174 67.6667 62.6587 68.6851 60.8457 70.498L56.8418 74.502C55.0288 76.3149 52.5701 77.3333 50.0062 77.3333H34.6771C15.9914 77.3333 0.84375 62.1857 0.84375 43.5C0.84375 24.8143 15.9914 9.66667 34.6771 9.66667H50.0062C52.5701 9.66667 55.0288 8.64828 56.8418 6.8353L60.8457 2.83129C62.6587 1.01846 65.1174 0 67.6813 0H83.0104C101.696 0 116.844 15.1477 116.844 33.8333C116.844 52.519 101.696 67.6667 83.0104 67.6667ZM67.6813 9.66667C65.1174 9.66667 62.6587 10.6851 60.8457 12.498L56.8418 16.502C55.0288 18.3149 52.5701 19.3333 50.0062 19.3333H34.6771C21.3302 19.3333 10.5104 30.1532 10.5104 43.5C10.5104 56.8468 21.3302 67.6667 34.6771 67.6667H50.0062C52.5701 67.6667 55.0288 66.6483 56.8418 64.8353L60.8457 60.8314C62.6587 59.0184 65.1174 58 67.6813 58H83.0104C96.3572 58 107.177 47.1801 107.177 33.8333C107.177 20.4866 96.3572 9.66667 83.0104 9.66667H67.6813Z" fill="currentColor"/>
						</svg>
					</div>
					<div>
						<p>Copyright © 2025 Socrates</p>
						<p>All rights reserved. Terms of Service & Privacy Policy.</p>
					</div>
				</div>
				<div class="bg-gray-200 text-gray-600 px-3 py-1 rounded text-xs font-medium">
					Status
				</div>
			</div>
		</footer>

	</main>
</div>

