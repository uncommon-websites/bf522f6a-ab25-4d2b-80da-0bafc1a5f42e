<script lang="ts">
	import { onMount } from 'svelte';

    // Data for sections
    const navLinks = ["Solutions", "Platform", "Integrations", "Security", "Company"];
    
    const logos = [
        { name: "Genentech", width: 100 },
        { name: "Amgen", width: 60 },
        { name: "Regeneron", width: 80 },
        { name: "Biogen", width: 70 },
        { name: "Moderna", width: 110 },
        { name: "Vertex", width: 120 },
        { name: "Illumina", width: 80 }
    ];

    const features = [
        {
            tag: "THERAPEUTIC INSIGHT",
            title: "Smart dashboards for deep genetic context",
            image: "analytics",
            color: "bg-gray-100"
        },
        {
            tag: "INTEROPERABILITY",
            title: "Seamlessly link assay results with LIMS and ELNs",
            image: "search",
            color: "bg-gray-100"
        },
        {
            tag: "DATA GOVERNANCE",
            title: "Enterprise-grade security and audit trails",
            image: "admin",
            color: "bg-gray-100"
        },
        {
            tag: "SCALABLE ANALYTICS",
            title: "Proprietary data graphs for biopharma R&D",
            image: "editor",
            color: "bg-gray-100"
        },
        {
            tag: "DECISION SUPPORT",
            title: "Actionable insights for clinical informatics",
            image: "phone",
            color: "bg-gray-100"
        },
        {
            tag: "PRECISION MEDICINE",
            title: "Surface relationships between variants and outcomes",
            image: "video",
            color: "bg-gray-100"
        }
    ];

    const testimonials = [
        {
            quote: "Helix Technologies has transformed how we connect our wet-lab results with genomic data. We no longer drown in fragmented assays.",
            name: "Dr. Sarah Chen",
            role: "Head of Genomic Discovery at BioVanguard",
            avatar: "SC"
        },
        {
            quote: "The first platform I've seen that truly understands the complexity of translational research data workflows.",
            name: "James Miller",
            role: "Director of R&D at Nexus Pharma",
            avatar: "JM"
        },
         {
            quote: "The interoperability with our existing ELNs was a game-changer. We went from pilot to full deployment in record time.",
            name: "Elena Rodriguez",
            role: "VP of Clinical Informatics",
            avatar: "ER"
        },
        {
            quote: "Helix provides the clarity we need to make time-critical therapeutic decisions. It's our platform of record.",
            name: "Dr. Marcus Thorne",
            role: "Chief Scientific Officer",
            avatar: "MT"
        },
        {
            quote: "The data governance and security practices are top-tier, satisfying even our most stringent institutional requirements.",
            name: "David Park",
            role: "IT Director at St. Jude's Research",
            avatar: "DP"
        },
        {
            quote: "It's not just a dashboard; it's a strategic asset for our precision medicine programs.",
            name: "Linda Wu",
            role: "Principal Scientist",
            avatar: "LW"
        }
    ];

    const partnershipServices = [
        "Dedicated computational biology lead",
        "Custom data pipeline integration",
        "Tailored R&D workflow onboarding",
        "Priority 24/7 technical support",
        "Legacy data migration services",
        "Clinical informatics consulting",
        "Compliance and security auditing"
    ];

    const comparisons = [
        {
            tag: "DATA INTEGRATION",
            left: "Fragmented assay results stored in siloed spreadsheets and legacy LIMS systems",
            right: "Unified data graph linking all assay outputs with deep genetic and patient context"
        },
        {
            tag: "INSIGHT GENERATION",
            left: "Manual cross-referencing of variants and clinical outcomes taking weeks",
            right: "Real-time visualization of therapeutic response and variant relationships"
        },
        {
            tag: "WORKFLOW",
            left: "Researchers spend 60% of their time on data wrangling and cleaning",
            right: "Automated pipelines allow scientists to focus entirely on therapeutic discovery"
        },
        {
            tag: "COMPLIANCE",
            left: "Difficult to track data lineage and maintain audit trails across tools",
            right: "Built-in enterprise governance with full audit logging and HIPAA compliance"
        },
        {
            tag: "SCALABILITY",
            left: "System slows down and breaks as genomic data volumes increase",
            right: "Cloud-native architecture designed for petabyte-scale genomic analysis"
        }
    ];

    const faqs = [
        "How does Helix integrate with our existing LIMS?",
        "What genomic data formats do you support?",
        "Is Helix Technologies HIPAA and GDPR compliant?",
        "Can we run Helix on our own private cloud?",
        "What is the typical timeline for a pilot phase?",
        "How do you handle data security and access controls?",
        "Do you provide support for clinical trial data?",
        "What kind of training do you offer for R&D teams?",
        "How does the proprietary data graph scale with our research?"
    ];

</script>

<div class="font-sans text-gray-900 bg-white selection:bg-primary-200 selection:text-black">
    <!-- Navbar -->
    <nav class="sticky top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 h-16 flex items-center justify-between">
            <div class="flex items-center gap-2">
                <!-- Logo Mark -->
                <svg width="28" height="28" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-600">
                    <path d="M12 2C6.47 2 2 6.47 2 12C2 17.53 6.47 22 12 22C17.53 22 22 17.53 22 12C22 6.47 17.53 2 12 2ZM15.63 15.63L14.21 17.05L12 14.84L9.79 17.05L8.37 15.63L10.58 13.42L8.37 11.21L9.79 9.79L12 12L14.21 9.79L15.63 11.21L13.42 13.42L15.63 15.63Z" fill="currentColor"/>
                    <path d="M12 4C7.58 4 4 7.58 4 12C4 16.42 7.58 20 12 20C16.42 20 20 16.42 20 12C20 7.58 16.42 4 12 4ZM12 18C8.69 18 6 15.31 6 12C6 8.69 8.69 6 12 6C15.31 6 18 8.69 18 12C18 15.31 15.31 18 12 18Z" fill="currentColor" opacity="0.3"/>
                </svg>
                <span class="font-medium text-lg tracking-tight">Helix Technologies</span>
            </div>

            <div class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-600">
                {#each navLinks as link}
                    <a href="#" class="hover:text-black transition-colors">{link}</a>
                {/each}
            </div>

            <button class="bg-primary-900 text-white px-5 py-2 rounded-full text-sm font-medium hover:bg-black transition-colors">
                Request a demo
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-20 pb-16 px-6 text-center overflow-hidden">
        <div class="max-w-4xl mx-auto mb-12">
            <h1 class="font-serif text-6xl md:text-7xl lg:text-[5rem] leading-[1.1] mb-6 font-normal tracking-tight">
                Therapeutic insight <br/> without the data chaos
            </h1>
            <p class="text-lg md:text-xl text-gray-600 max-w-2xl mx-auto mb-8 leading-relaxed">
                Helix Technologies helps biopharma and clinical R&D teams make sense of assay and genomic data—fast, securely, and at scale.
            </p>
            <div class="flex flex-col sm:flex-row justify-center gap-4">
                <button class="bg-primary-500 text-white px-8 py-3 rounded-full text-base font-medium hover:bg-primary-600 transition-colors">
                    Request a demo
                </button>
                <button class="bg-white text-black border border-gray-200 px-8 py-3 rounded-full text-base font-medium hover:bg-gray-50 transition-colors">
                    Watch platform tour
                </button>
            </div>
        </div>

        <!-- Hero Image Collage Mockup -->
        <div class="relative max-w-[1200px] mx-auto h-[400px] md:h-[600px] mt-12">
            <div class="relative w-full h-full flex justify-center items-end">
                <img 
                    src="/generated/image-a-clean-modern-laboratory-setting-with-a-1768959013264-0.webp" 
                    alt="Helix Platform in Action" 
                    class="w-full h-full object-cover rounded-2xl shadow-2xl border border-gray-100"
                />
                <div class="absolute inset-0 bg-gradient-to-t from-white/20 to-transparent pointer-events-none"></div>
            </div>
        </div>
    </section>

    <!-- Logos Section -->
    <section class="py-16 border-b border-gray-100">
        <div class="max-w-[1400px] mx-auto px-6 text-center">
            <p class="text-sm text-gray-500 mb-10 uppercase tracking-widest">Powering the next frontier of medicine</p>
            <div class="flex flex-wrap justify-center items-center gap-12 md:gap-16 opacity-70 grayscale hover:grayscale-0 transition-all duration-500">
                {#each logos as logo}
                    <div class="h-8 flex items-center justify-center">
                        <span class="font-bold text-xl font-serif italic text-gray-400">{logo.name}</span>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Meet Helix Grid -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">From raw data to ready decisions</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Stop digging through spreadsheets and siloed systems. Our smart dashboards connect results from your existing assays with genetic context and patient-level metadata.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                {#each features as feature}
                    <div class="group bg-white rounded-2xl overflow-hidden shadow-sm hover:shadow-md transition-shadow duration-300 flex flex-col h-[500px]">
                        <div class="p-8 pb-0 flex-1">
                            <span class="inline-block bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded mb-4 uppercase">
                                {feature.tag}
                            </span>
                            <h3 class="font-serif text-2xl leading-tight mb-4">
                                {feature.title}
                            </h3>
                        </div>
                        <div class="h-[300px] bg-gray-100 relative overflow-hidden mt-4 mx-4 rounded-t-xl group-hover:translate-y-[-5px] transition-transform duration-500">
                            {#if feature.image === 'analytics'}
                                <img src="/generated/image-close-up-of-a-high-resolution-monitor-di-1768959016107-1.webp" alt={feature.title} class="w-full h-full object-cover" />
                            {:else}
                                <div class="absolute inset-0 bg-gradient-to-br from-primary-50 to-white flex items-center justify-center p-8">
                                    <div class="w-full h-full border-2 border-dashed border-primary-200 rounded-lg flex items-center justify-center text-primary-300 font-serif italic">
                                        Helix {feature.tag} Interface
                                    </div>
                                </div>
                            {/if}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
            <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Built for teams <br/> doing serious science</h2>
                <p class="text-lg text-gray-600 leading-relaxed mb-10">
                    Trusted by leading biopharma and clinical research organizations worldwide.
                </p>
            </div>

            <div class="columns-1 md:columns-2 lg:columns-3 gap-6 space-y-6">
                {#each testimonials as testimonial}
                    <div class="break-inside-avoid bg-gray-50 p-8 rounded-2xl border border-gray-100">
                        <p class="text-lg leading-relaxed mb-6 italic text-gray-700">"{testimonial.quote}"</p>
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 bg-primary-900 rounded-full flex items-center justify-center text-sm font-bold text-white">
                                {testimonial.avatar}
                            </div>
                            <div>
                                <div class="font-medium">{testimonial.name}</div>
                                <div class="text-sm text-gray-500">{testimonial.role}</div>
                            </div>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Partnership Section -->
    <section class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">Built by experts, <br/> for experts</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    We're not another lab. We’re software-first, focused on giving R&D leaders the clarity they need—without disrupting existing workflows.
                </p>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="bg-gray-900 text-white p-12 rounded-3xl h-full">
                    <h3 class="font-serif text-2xl mb-8">Enterprise partnership services</h3>
                    <ul class="space-y-4">
                        {#each partnershipServices as service}
                            <li class="flex items-center gap-3">
                                <div class="w-5 h-5 rounded-full bg-primary-500 flex items-center justify-center shrink-0">
                                    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"></polyline></svg>
                                </div>
                                <span class="text-gray-300">{service}</span>
                            </li>
                        {/each}
                    </ul>
                </div>
                <div class="h-full min-h-[500px] rounded-3xl overflow-hidden relative">
                    <img src="/generated/image-a-wide-shot-of-a-modern-biopharma-resear-1768959020731-3.webp" alt="Helix Team Collaboration" class="absolute inset-0 w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-700" />
                </div>
            </div>
        </div>
    </section>

    <!-- Case Studies Section -->
    <section class="py-24 px-6 bg-gray-50">
        <div class="max-w-[1400px] mx-auto">
            <div class="flex justify-between items-end mb-12">
                <div>
                    <h2 class="font-serif text-4xl mb-4">Insights that keep up with your pipeline</h2>
                    <p class="text-lg text-gray-600 max-w-xl">Read how Helix Technologies is accelerating discovery across the industry.</p>
                </div>
                <div class="flex gap-2">
                    <button class="w-10 h-10 rounded-full border border-gray-200 flex items-center justify-center hover:bg-white">
                        ←
                    </button>
                    <button class="w-10 h-10 rounded-full bg-black text-white flex items-center justify-center hover:bg-gray-800">
                        →
                    </button>
                </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Card 1 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                        <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                        <img src="/generated/image-a-diverse-team-of-computational-biologis-1768959018092-2.webp" alt="Case Study" class="w-full h-full object-cover mix-blend-overlay opacity-60 group-hover:scale-105 transition-transform duration-700" />
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Accelerating precision oncology trials by 40%</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Focus: Oncology <br/> Impact: Rapid Patient Stratification</div>
                        </div>
                        <div class="font-bold text-xl">Global Biopharma Partner</div>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                         <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                         <div class="absolute inset-0 bg-primary-900/40 mix-blend-overlay"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Mapping 10M+ variants to therapeutic response</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Focus: Rare Disease <br/> Impact: Novel Target Identification</div>
                        </div>
                        <div class="font-bold text-xl">Genomics Institute</div>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="aspect-[4/5] relative rounded-2xl overflow-hidden group cursor-pointer">
                    <div class="absolute inset-0 bg-gray-900">
                         <div class="absolute inset-0 opacity-50 bg-gradient-to-t from-black via-transparent to-transparent"></div>
                         <div class="absolute inset-0 bg-primary-500/20 mix-blend-overlay"></div>
                    </div>
                    <div class="absolute inset-0 p-8 flex flex-col justify-between text-white">
                        <div>
                            <h3 class="font-serif text-3xl leading-tight mb-4">Integrating 50+ disparate lab systems into one view</h3>
                            <div class="text-xs text-gray-300 uppercase tracking-wider">Focus: Enterprise R&D <br/> Impact: Data Interoperability</div>
                        </div>
                        <div class="font-bold text-xl">Top 10 Pharma Client</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Comparison Section -->
    <section class="py-24 px-6 bg-white">
        <div class="max-w-[1400px] mx-auto">
             <div class="text-center max-w-3xl mx-auto mb-20">
                <h2 class="font-serif text-5xl md:text-6xl mb-6">The Helix Advantage</h2>
                <p class="text-lg text-gray-600 leading-relaxed">
                    Transform your team from a data wrangling machine <br/> to a strategic therapeutic value-driver.
                </p>
            </div>

            <div class="border-t border-gray-100">
                <div class="grid grid-cols-3 py-4 text-xs text-gray-400 uppercase tracking-wider border-b border-gray-100">
                    <div>Legacy Workflows</div>
                    <div class="text-center">→</div>
                    <div>Helix Technologies</div>
                </div>
                {#each comparisons as item}
                    <div class="grid grid-cols-1 md:grid-cols-[1fr_auto_1fr] gap-8 py-12 border-b border-gray-100 items-center group hover:bg-gray-50 transition-colors px-4 -mx-4 rounded-xl">
                        <div class="text-gray-500 leading-relaxed md:pr-8">
                            {item.left}
                        </div>
                        <div class="flex justify-center">
                            <span class="bg-primary-100 text-primary-800 text-[10px] font-bold tracking-wider px-2 py-1 rounded uppercase whitespace-nowrap">
                                {item.tag}
                            </span>
                        </div>
                        <div class="text-black font-medium leading-relaxed md:pl-8">
                            {item.right}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Mission Section -->
    <section class="py-24 px-6">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-2 min-h-[600px] rounded-3xl overflow-hidden shadow-2xl">
            <div class="bg-gray-900 relative flex items-center justify-center p-12 overflow-hidden">
                <div class="text-white text-center">
                    <h3 class="font-serif text-5xl mb-6">Building the Future of Medicine</h3>
                    <p class="text-primary-400 text-xl font-medium">A New Frontier for Healthcare</p>
                </div>
            </div>
            <div class="bg-primary-500 p-12 lg:p-24 flex flex-col justify-center text-white">
                <p class="font-serif text-3xl md:text-4xl leading-tight mb-8">
                    Helix Technologies is on a mission to transform how R&D teams access and act on biological knowledge.
                </p>
                <p class="font-serif text-3xl md:text-4xl leading-tight opacity-90">
                    We believe the intersection of bioinformatics and clinical informatics is where the next decade of therapeutic breakthroughs will be born.
                </p>
            </div>
        </div>
    </section>

    <!-- Bottom CTA -->
    <section class="py-32 px-6 text-center bg-white">
        <div class="max-w-4xl mx-auto">
            <h2 class="font-serif text-6xl md:text-7xl mb-6">Ready to unlock your <br/> therapeutic data?</h2>
            <p class="text-xl text-gray-600 mb-10">Join the biopharma innovators already using Helix.</p>
            <button class="bg-primary-900 text-white px-8 py-3 rounded-full text-base font-medium hover:bg-black transition-colors">
                Request a demo today
            </button>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-24 px-6 bg-gray-50 border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto">
            <h2 class="font-serif text-5xl mb-16">Frequently Asked Questions</h2>
            <div class="space-y-4">
                {#each faqs as faq}
                    <div class="border-b border-gray-200 py-6 flex justify-between items-center cursor-pointer group hover:bg-white px-4 -mx-4 rounded-lg transition-colors">
                        <span class="text-lg font-medium">{faq}</span>
                        <div class="w-8 h-8 rounded-full bg-primary-900 text-white flex items-center justify-center group-hover:bg-black transition-colors">
                            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="py-24 px-6 bg-white border-t border-gray-100">
        <div class="max-w-[1400px] mx-auto grid grid-cols-1 md:grid-cols-4 gap-12">
            <div class="col-span-1 md:col-span-1">
                <div class="flex items-center gap-2 mb-8">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="text-primary-600">
                        <path d="M12 2C6.47 2 2 6.47 2 12C2 17.53 6.47 22 12 22C17.53 22 22 17.53 22 12C22 6.47 17.53 2 12 2ZM15.63 15.63L14.21 17.05L12 14.84L9.79 17.05L8.37 15.63L10.58 13.42L8.37 11.21L9.79 9.79L12 12L14.21 9.79L15.63 11.21L13.42 13.42L15.63 15.63Z" fill="currentColor"/>
                    </svg>
                    <span class="font-medium text-xl tracking-tight">Helix Technologies</span>
                </div>
                <div class="text-sm text-gray-500 mb-4">Subscribe to our R&D insights</div>
                <div class="flex gap-2 border-b border-gray-200 pb-2 mb-8">
                    <input type="email" placeholder="Email address" class="w-full outline-none text-sm" />
                    <button class="text-gray-400 hover:text-black">→</button>
                </div>
                <div class="text-xs text-gray-400">© 2025 Helix Technologies Inc. All rights reserved.</div>
            </div>

            <div class="grid grid-cols-2 md:grid-cols-3 gap-8 col-span-1 md:col-span-3">
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Platform</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Smart Dashboards</a></li>
                        <li><a href="#" class="hover:text-black">Genomic Context</a></li>
                        <li><a href="#" class="hover:text-black">Assay Integration</a></li>
                        <li><a href="#" class="hover:text-black">Data Graphs</a></li>
                        <li><a href="#" class="hover:text-black">Security</a></li>
                        <li><a href="#" class="hover:text-black">Pricing</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Solutions</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Drug Discovery</a></li>
                        <li><a href="#" class="hover:text-black">Clinical R&D</a></li>
                        <li><a href="#" class="hover:text-black">Precision Medicine</a></li>
                        <li><a href="#" class="hover:text-black">Bioinformatics</a></li>
                        <li><a href="#" class="hover:text-black">Case Stories</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-xs font-bold text-gray-400 uppercase tracking-wider mb-6">Company</h4>
                    <ul class="space-y-3 text-sm text-gray-600">
                        <li><a href="#" class="hover:text-black">Our Mission</a></li>
                        <li><a href="#" class="hover:text-black">Careers</a></li>
                        <li><a href="#" class="hover:text-black">Press</a></li>
                        <li><a href="#" class="hover:text-black">Legal & Privacy</a></li>
                        <li><a href="#" class="hover:text-black">Contact</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>

</div>

