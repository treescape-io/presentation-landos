# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Reveal.js-based presentation for Treescape, an AI-powered agroforestry platform. The presentation is designed for a 5-minute pitch at the Dutch Embassy "Unlocking Land Potential" event.

**Presentation Goal**: Challenge to present the vision of making agroforestry viable at scale using AI, algorithms, and open data - with clear calls to action for founding pilot customers, CEO partnership, research collaborations, and other partnerships.

**Time Constraint**: ONLY 5 MINUTES for the entire presentation. Every slide and transition must be optimized for this strict time limit.

**Target Audience**: Mixed group including:
- Start-ups and entrepreneurs
- Academics and researchers
- Municipality/CIM (Comunidade Intermunicipal) representatives
- Consultants
- Agricultural sector professionals
- Renewables sector professionals
- GIS/EO (Geographic Information Systems/Earth Observation) experts
- Legal professionals

## Architecture

**Single-file HTML presentation**: The entire presentation is contained in `index.html` with:
- Embedded CSS styles in the `<style>` block (lines 32-130)
- Slide content in nested `<section>` elements within `.reveal .slides` (lines 135-481)
- Reveal.js configuration in inline `<script>` block (lines 486-510)
- External dependencies loaded via CDN (Reveal.js 4.3.1)

**No build process**: This is a static HTML file that can be opened directly in a browser.

## Running/Viewing the Presentation

```bash
# Simple Python HTTP server
python3 -m http.server 8000
# Then open: http://localhost:8000

# Or just open the file directly
open index.html
```

**Presentation controls**:
- Arrow keys or space to navigate slides
- Press 'S' to open speaker notes window
- Press 'F' for fullscreen
- Press 'ESC' for slide overview

## Content Structure & Flow

The presentation follows this narrative arc (total: 5 minutes):

1. **Personal Journey** (0:45s): Tech entrepreneur → food forest pioneer in Silverto
2. **The Crisis** (0:45s): Demographics, eucalyptus monocultures, climate emergency
3. **The Problem** (0:15s): Why isn't agroforestry everywhere? COMPLEXITY
4. **The Solution** (1:00s): Treescape's 3-pillar approach (AI/algorithms/data)
5. **Portugal's Opportunity** (0:20s): Unique positioning for regenerative revolution
6. **Scaling Strategy** (0:15s): 10ha → 100ha → 1000ha iterative approach
7. **Partnerships CTA** (0:15s): Research, CEO partner, pilot customers
8. **Mission & Close** (0:25s): 1 billion hectares globally, starting in Portugal

**Supporting files**:
- `pitch.md`: Full 5-minute pitch script with timing breakdowns, Q&A preparation, and delivery notes
- `presentation_images_guide.md`: Image requirements and placeholder documentation
- `images/`: Directory containing presentation media (images and video)

**Reveal.js configuration** (lines 487-509):
- Configured for 5-minute presentation (totalTime: 300 seconds)
- Slide dimensions: 1920x1080
- Auto-slide disabled by default (autoSlide: 0)
- Each slide has `data-timing` attribute indicating suggested time in seconds
- Speaker notes enabled via RevealNotes plugin

## Styling Approach

**Color scheme**:
- Primary brand color: `#8fc742` (green) - used for `.highlight` class and headings
- Danger/urgent: `#ff6b6b` (red) - used for crisis statistics
- Dark theme with black background

**Key CSS classes**:
- `.highlight`: Brand green color for emphasis
- `.danger`: Red color for crisis/urgent content
- `.stat`: Large bold statistics (3em font-size)
- `.lightbackground`: Text shadow for readability over bright images
- `.compact`: Tighter spacing for list items
- `.noborder`: Remove borders/shadows from images
- `.logo`: Circular clip-path for avatar image

## Editing the Presentation

**To modify slide content**: Edit the `<section>` elements in `index.html` starting at line 135

**To adjust styling**: Modify the `<style>` block (lines 32-130)

**To add new slides**: Insert new `<section>` elements with appropriate `data-background-*` attributes:
```html
<section
  data-background-image="images/filename.jpg"
  data-background-opacity="0.3"
  data-timing="15"
>
  <h2>Slide Title</h2>
  <aside class="notes">Speaker notes here</aside>
</section>
```

**IMPORTANT: Time management**: When adding or modifying slides, update the `data-timing` attributes and ensure the total stays at or below 300 seconds (5 minutes).

**Media assets**: Place images/videos in the `images/` directory and reference them with relative paths

## Key Technical Concepts to Maintain

When editing content, preserve these core technical differentiators for the GIS/EO and technical audience members:

- **Genetic Algorithms** for plant placement optimization (not ML - explainable)
- **Multi-/hyper-spectral Earth Observation (EO)** data integration
- **Plant-level data representation** from field to national scale
- **60-year biophysical projections** with bankable outcomes
- **Guided Agentic Intelligence** for natural conversation-based design
- **Partnership with WUR spinoff Farmtree** for modeling credibility

## Dependencies

All dependencies loaded from CDN (no package.json or node_modules):
- Reveal.js 4.3.1 (core framework)
- Reveal.js Notes plugin (speaker notes)
- Reset and theme CSS from Reveal.js

No local installation or build tools required.
