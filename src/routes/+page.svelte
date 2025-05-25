<script>
    import { onMount } from 'svelte';
    
    onMount(() => {
        // Add interactive hover effects
        const links = document.querySelectorAll('a[href^="/"]');
        links.forEach(link => {
            link.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-2px)';
            });
            link.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0)';
            });
        });
    });
</script>

<svelte:head>
    <title>MinStreamer</title>
    <meta name="description" content="Demystify video streaming in the browser with MinStreamer" />
</svelte:head>

<style>
    @keyframes float {
        0%, 100% { transform: translateY(0px); }
        50% { transform: translateY(-10px); }
    }
    @keyframes pulse-slow {
        0%, 100% { opacity: 0.4; }
        50% { opacity: 0.8; }
    }
    .float-animation { 
        animation: float 6s ease-in-out infinite; 
    }
    .pulse-slow { 
        animation: pulse-slow 3s ease-in-out infinite; 
    }
    .gradient-text {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
</style>

<div class="bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 min-h-screen text-white">
    <!-- Background Effects -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none">
        <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-purple-500/10 rounded-full blur-3xl pulse-slow"></div>
        <div class="absolute bottom-1/4 right-1/4 w-80 h-80 bg-blue-500/10 rounded-full blur-3xl pulse-slow" style="animation-delay: 1s;"></div>
        <div class="absolute top-3/4 left-1/2 w-64 h-64 bg-indigo-500/10 rounded-full blur-3xl pulse-slow" style="animation-delay: 2s;"></div>
    </div>

    <!-- Navigation -->
    <nav class="relative z-10 flex justify-between items-center p-6 backdrop-blur-sm bg-white/5 border-b border-white/10">
        <div class="flex items-center space-x-3">
            <div class="w-8 h-8 bg-gradient-to-r from-purple-500 to-blue-500 rounded-lg flex items-center justify-center">
                <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h1.5a4.5 4.5 0 011.5 1.5V14a4.5 4.5 0 01-3 4.243M21 12a9 9 0 11-6.219-8.56"/>
                </svg>
            </div>
            <h1 class="text-2xl font-bold gradient-text">MinStreamer</h1>
        </div>
        <div class="flex space-x-4">
            <a href="/login" class="px-4 py-2 text-slate-300 hover:text-white transition-colors duration-200 hover:bg-white/10 rounded-lg">
                Login
            </a>
            <a href="/register" class="px-6 py-2 bg-gradient-to-r from-purple-600 to-blue-600 hover:from-purple-700 hover:to-blue-700 rounded-lg font-medium transition-all duration-200 transform hover:scale-105 shadow-lg hover:shadow-purple-500/25">
                Register
            </a>
        </div>
    </nav>

    <!-- Main Content -->
    <main class="relative z-10 container mx-auto px-6 py-16">
        <!-- Hero Section -->
        <div class="text-center mb-20">
            <div class="float-animation mb-8">
                <div class="w-24 h-24 mx-auto bg-gradient-to-r from-purple-500 to-blue-500 rounded-2xl flex items-center justify-center shadow-2xl shadow-purple-500/25">
                    <svg class="w-12 h-12 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z"/>
                    </svg>
                </div>
            </div>
            <h2 class="text-5xl md:text-6xl font-bold mb-6 leading-tight">
                Demystify Video 
                <span class="gradient-text">Streaming</span>
            </h2>
        </div>

        <!-- Project Description -->
        <section class="mb-16">
            <div class="max-w-4xl mx-auto">
                <div class="backdrop-blur-sm bg-white/5 rounded-2xl p-8 border border-white/10 shadow-2xl hover:bg-white/10 transition-all duration-300">
                    <p class="text-xl text-slate-200 leading-relaxed text-center">
                        MinStreamer is a simple project dedicated to <span class="text-purple-300 font-semibold">demystifying video streaming in the browser</span>, 
                        and providing a template for <span class="text-blue-300 font-semibold">fullstack FastAPI applications</span>.
                    </p>
                </div>
            </div>
        </section>

        <!-- Tech Stack and Hosting Grid -->
        <div class="grid md:grid-cols-2 gap-8 max-w-6xl mx-auto">
            <!-- Tech Stack -->
            <section class="backdrop-blur-sm bg-white/5 rounded-2xl p-8 border border-white/10 shadow-2xl hover:bg-white/10 transition-all duration-300">
                <div class="flex items-center mb-6">
                    <div class="w-10 h-10 bg-gradient-to-r from-green-500 to-emerald-500 rounded-lg flex items-center justify-center mr-4">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"/>
                        </svg>
                    </div>
                    <h3 class="text-2xl font-bold text-white">Tech Stack</h3>
                </div>
                <div class="space-y-3">
                    {#each [
                        { name: 'SvelteKit', color: 'bg-orange-500' },
                        { name: 'FastAPI', color: 'bg-green-500' },
                        { name: 'PostgreSQL', color: 'bg-blue-500' },
                        { name: 'Redis', color: 'bg-red-500' },
                        { name: 'Ory Kratos', color: 'bg-purple-500' }
                    ] as tech}
                        <div class="flex items-center p-3 rounded-lg hover:bg-white/10 transition-colors duration-200">
                            <div class="w-2 h-2 {tech.color} rounded-full mr-3"></div>
                            <span class="text-slate-200 font-medium">{tech.name}</span>
                        </div>
                    {/each}
                </div>
            </section>

            <!-- Hosting -->
            <section class="backdrop-blur-sm bg-white/5 rounded-2xl p-8 border border-white/10 shadow-2xl hover:bg-white/10 transition-all duration-300">
                <div class="flex items-center mb-6">
                    <div class="w-10 h-10 bg-gradient-to-r from-cyan-500 to-blue-500 rounded-lg flex items-center justify-center mr-4">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01"/>
                        </svg>
                    </div>
                    <h3 class="text-2xl font-bold text-white">Hosting</h3>
                </div>
                <div class="space-y-4">
                    <div class="p-4 rounded-lg bg-gradient-to-r from-orange-500/20 to-orange-600/20 border border-orange-500/30">
                        <div class="flex items-center">
                            <span class="text-orange-300 font-semibold mr-2">Frontend:</span>
                            <span class="text-white font-medium">Cloudflare</span>
                        </div>
                    </div>
                    <div class="p-4 rounded-lg bg-gradient-to-r from-purple-500/20 to-purple-600/20 border border-purple-500/30">
                        <div class="flex items-center">
                            <span class="text-purple-300 font-semibold mr-2">Backend:</span>
                            <span class="text-white font-medium">Railway</span>
                        </div>
                    </div>
                </div>
            </section>
        </div>

        <!-- Call to Action -->
        <div class="text-center mt-16">
            <div class="inline-flex items-center space-x-4 backdrop-blur-sm bg-white/5 rounded-2xl p-6 border border-white/10">
                <span class="text-slate-300">Ready to explore video streaming?</span>
                <a href="/register" class="px-8 py-3 bg-gradient-to-r from-purple-600 to-blue-600 hover:from-purple-700 hover:to-blue-700 rounded-lg font-medium transition-all duration-200 transform hover:scale-105 shadow-lg hover:shadow-purple-500/25">
                    Get Started
                </a>
            </div>
        </div>
    </main>
</div>