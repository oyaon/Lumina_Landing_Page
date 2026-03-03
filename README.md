#Lumina — Landing Page

The Intelligence Layer for Visionary Teams

A dark luxury single-page marketing site for Lumina v2. Single self-contained index.html — no build step, no frameworks, no dependencies beyond Google Fonts.

Quick Start
bash
open index.html
or
python3 -m http.server 8080

Page Sections
#SectionDescription1NavigationFixed. Logo mark, 4 nav links, Sign In, Begin Free CTA. Glazes dark on scroll.2HeroFull-viewport. Headline, subtext, dual CTAs, trust strip, scroll indicator.3Stats Bar4 animated counters — 340K+ Teams · 98.9% Uptime · 12ms Latency · 4.9★4Features6-card grid. Card 01 spans full width with live node-graph. Cards 02–06 in 3-col.5Platform SpotlightAnimated orbital system + 3 philosophy accordion items.6Pricing3 tiers: Ember · Luminary · Sovereign. Monthly/annual toggle.7TestimonialsDual infinite-scroll marquee rows (opposing). 10 personas.8CTAEmail capture with focus-glow state + trust strip.9Footer4-column: Brand · Product · Developers · Company.

Design Tokens
css--gold:       #c9a84c;
--gold-light: #e8c97a;
--gold-dim:   #6b5526;
--bg:         #060606;
--bg2:        #0c0c0c;
--bg3:        #131313;
--text:       #ede8df;
--text-mid:   #9e9890;
--text-dim:   #52504c;
--border:     rgba(201,168,76,.12);
--border-hi:  rgba(201,168,76,.28);
Typefaces: Cormorant Garamond (headlines) · Outfit (body) · DM Mono (labels)

Animations
ElementMethodDurationCustom cursorJS rAF lerp 0.11ContinuousHero orbsCSS orbDrift18–24sHero contentCSS fadeUp staggered0.3–1.5sStat countersJS setInterval1600msFeature cardsIntersectionObserver0.55s staggeredNode graphCSS nodePulse3sOrbital ringsCSS visRotate18–38sTestimonial marqueeCSS marquee42s / 52s reversePricing toggleJS clickInstant

Breakpoints
BreakpointKey Changes≤ 1100pxNav links hidden · Features 3→2 col · Pricing stacks · Footer 2-col≤ 640pxFeatures 1-col · Stats 2×2 · Hero actions full-width · Footer 1-col

Brand Voice Rules

"Crafted", never "engineered"
Commands, not invitations — all headlines declarative
Single action verb: Begin (Begin Free · Begin Luminary · Begin Free →)
No real brand names in the trust strip (Notion/Linear/Vercel removed)
"Teams" not "builders" throughout


Known Improvements Needed
ItemPriorityProduct screenshot / demo videoHighReal customer logosHighOpen Graph / Twitter Card / JSON-LDMediumprefers-reduced-motion supportMediumKeyboard focus ringsMediumMobile nav drawerLow
