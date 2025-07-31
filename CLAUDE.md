# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Deep Sea Classified - Project Context for Claude

## Project Overview

**Deep Sea Classified** is an immersive web presentation about a fictional deep-sea expedition that encounters a colossal squid. The project uses cutting-edge web technologies to create a cinematic, classified document aesthetic with oceanic themes and sci-fi elements.

## Theme & Aesthetic

- **Genre**: Sci-fi thriller / Deep sea exploration documentary
- **Visual Style**: Classified military/scientific documents with oceanic elements
- **Color Palette**:
  - Deep ocean blues (#0A0E27, #1A237E, #0D1421)
  - Bioluminescent cyan (#00E5FF, #00FF88)
  - Alert colors (#FF4500, #FF4444)
  - Text colors (#E3F2FD, #81C784)
- **Typography**:
  - Headlines: 'Orbitron' (sci-fi/tech feel)
  - Body/UI: 'Inter' (clean, readable)
  - Technical/Code: 'JetBrains Mono' (monospace)

## Current File Structure

```text
/workspaces/deepseasquid/
├── index.html                # Main landing page with mysterious atmosphere
├── figma_intro_slide.html    # Slide 01: Classified intro with mission briefing
├── figma_descent_slide.html  # Slide 02: Ocean descent through depth zones
├── encounter_slide.html      # Slide 03: First contact with the colossal squid
├── video_encounter_slide.html # Slide 04: Classified footage (placeholder)
├── analysis_slide.html       # Slide 05: Biological analysis and specimen data
├── escape_slide.html         # Slide 06: Emergency ascent sequence
├── README.md                 # Project documentation
├── LICENSE                   # Project license
└── CLAUDE.md                # This context file
```

## Design Patterns & Conventions

### CSS Architecture

- **Reset**: Universal `* { margin: 0; padding: 0; box-sizing: border-box; }`
- **Backgrounds**: Complex gradients simulating ocean depths
- **Animations**: Smooth, oceanic movements (floating, pulsing, waves)
- **Effects**: Backdrop blur, drop shadows, glowing elements
- **Responsive**: Mobile-first with `@media (max-width: 768px)`

### Animation Principles

- **Timing**: Use ease-in-out for natural movement
- **Duration**: 2-8 seconds for ambient animations
- **Delays**: Stagger animations with `animation-delay`
- **Infinite loops**: For ambient effects (particles, glow, pulse)
- **One-time**: For reveals and transitions (`forwards` fill-mode)

### UI Components

- **Classification Headers**: Red alert-style warnings at top
- **Status Indicators**: Pulsing dots with status text
- **Data Boxes**: Glass-morphism cards with hover effects
- **Coordinates**: Monospace text positioning data
- **Particles**: Floating bioluminescent elements

## Content Structure

### Narrative Flow

1. **Intro Slide**: Mission briefing and classification
2. **Descent Slide**: Journey through ocean layers with depth gauge
3. **Encounter Slide**: First contact with massive creature
4. **Video Footage**: Classified recorded footage (placeholder)
5. **Analysis Slide**: Scientific data and behavioral assessment
6. **Escape Slide**: Emergency ascent sequence

### Data Elements

- **Location**: South Sandwich Islands
- **Coordinates**: LAT: -59.4263°S, LON: -27.0434°W
- **Depth**: 1,968 feet
- **Date**: March 9, 2025 (first contact)
- **Species**: Mesonychoteuthis hamiltoni (Colossal Squid)
- **Size**: 46 meters (unprecedented)

## Development Commands

### Local Development

```bash
# Serve locally (no build process required)
python -m http.server 8000
# or
python3 -m http.server 8000
# or any local server of choice

# Open in browser
open http://localhost:8000
```

### No Build Process

- This project uses vanilla HTML, CSS, and minimal JavaScript
- No package.json, build tools, or dependencies
- Simply open HTML files directly in browser or serve via local server
- All slides are self-contained HTML files with embedded CSS

### Testing

- Manual testing by opening each HTML file in browser
- Test animations and responsiveness across different screen sizes
- Verify all slides work in presentation mode (F11)
- No automated test framework present

## Technical Requirements

### Browser Compatibility

- Modern browsers supporting CSS Grid, Flexbox, CSS animations
- No external JavaScript dependencies (pure CSS animations)
- Responsive design for mobile/tablet/desktop

### Performance Considerations

- Optimize animations for 60fps
- Use `transform` and `opacity` for GPU acceleration
- Minimize repaints with `will-change` when necessary
- Keep particle counts reasonable for performance

### Accessibility

- Maintain readable contrast ratios
- Provide fallbacks for reduced motion preferences
- Ensure keyboard navigation where applicable

## Code Style Guidelines

### HTML

- Semantic structure with clear class naming
- Comment major sections
- Use data attributes for dynamic content
- Maintain proper document structure

### CSS

- BEM-like naming convention (`.component__element--modifier`)
- Group related styles (layout, typography, animations)
- Use CSS custom properties for theme values
- Comment complex animations and calculations

### Naming Conventions

- **Classes**: Descriptive, hyphenated (`.particle`, `.sonar-sweep`)
- **Animations**: Action-based names (`@keyframes bioFloat`)
- **Colors**: Semantic names in comments
- **Timing**: Document animation durations

## Development Guidelines

### When Adding New Pages

1. Maintain consistent header/footer elements
2. Follow the narrative progression
3. Use similar particle/ambient systems
4. Keep classification/status elements
5. Ensure responsive design

### Animation Best Practices

- Start with subtle effects, enhance gradually
- Test on different screen sizes
- Consider reduced motion preferences
- Use hardware acceleration (`transform3d`, `translateZ`)

### Content Guidelines

- Maintain scientific accuracy where possible
- Keep the "classified document" tone
- Use technical jargon appropriately
- Build tension through progressive revelation

## Common Patterns to Reuse

### Particle Systems

```css
.particle {
    position: absolute;
    background: #00E5FF;
    border-radius: 50%;
    opacity: 0.1;
    animation: float 6s ease-in-out infinite;
}
```

### Glass Morphism Cards

```css
.info-box {
    background: rgba(26, 35, 126, 0.3);
    border: 1px solid #00E5FF;
    backdrop-filter: blur(10px);
    border-radius: 8px;
}
```

### Status Indicators

```css
.status-indicator {
    width: 12px;
    height: 12px;
    background: #FF4500;
    border-radius: 50%;
    animation: pulse 1.5s ease-in-out infinite;
}
```

## Future Expansion Ideas

- **Escape Sequence**: Dramatic getaway from aggressive creature
- **Data Analysis**: Scientific breakdown of the encounter
- **Cover-up**: Government classification and secrecy
- **Interactive Elements**: Click-through navigation
- **Sound Design**: Ambient ocean sounds and sonar pings
- **Video Integration**: Simulated deep-sea footage

## AI Collaboration Guidelines (Claude + Kilo Code)

When working with multiple AI editors simultaneously on this codebase, follow these protocols to ensure smooth collaboration:

### Communication Protocol

**Before Making Changes:**
- Always announce your intended changes in comments: `<!-- CLAUDE: Adding new particle animation -->`
- Check for recent edits by other AI: Look for `<!-- KILO:` or similar markers
- Scan the git status/recent commits for concurrent work

**Change Markers:**
```html
<!-- AI_EDIT_START: CLAUDE - [timestamp] - [brief description] -->
[your changes here]
<!-- AI_EDIT_END: CLAUDE -->
```

### File Management

**Avoid Simultaneous Edits:**
- Check file modification timestamps before editing
- If a file was modified in the last 2 minutes, coordinate before proceeding
- Use `git status` to see what's currently being worked on

**Safe Zones for Parallel Work:**
- **Different files**: Work on separate HTML files simultaneously
- **CSS sections**: Different animation keyframes or component styles
- **Documentation**: README updates vs code changes

**High-Risk Zones:**
- Shared CSS variables and global styles
- Common HTML structures (headers, particles)
- JavaScript event handlers (if added)

### Code Style Consistency

**Maintain Unified Patterns:**
- Follow the existing naming conventions established in this project
- Use the same animation timing functions and durations
- Keep consistent indentation and spacing
- Reference the "Common Patterns to Reuse" section above

**Version Control Best Practices:**
- Make atomic commits with clear messages
- Include AI identification: `git commit -m "CLAUDE: Add creature reveal animation"`
- Pull/sync before major changes
- Create branches for experimental features

### Conflict Resolution

**If Conflicts Occur:**
1. **Immediate Communication**: Leave a comment explaining the conflict
2. **Preserve Both Approaches**: Comment out conflicting code rather than deleting
3. **Document Decisions**: Add comments explaining why one approach was chosen
4. **Test Integration**: Ensure both AI contributions work together

**Example Conflict Resolution:**
```css
/* CONFLICT RESOLUTION: Both Claude and Kilo added glow effects */
/* CLAUDE approach - more subtle */
/* .title { text-shadow: 0 0 20px #00E5FF; } */

/* KILO approach - more dramatic (CHOSEN) */
.title { text-shadow: 0 0 30px #00E5FF, 0 0 50px #00E5FF; }

/* INTEGRATED: Combining both with animation variance */
.title {
    text-shadow: 0 0 25px #00E5FF;
    animation: variableGlow 4s ease-in-out infinite;
}
```

### Coordination Strategies

**Work Distribution:**
- **Claude**: Focus on narrative content, animations, responsive design
- **Kilo**: Focus on interactivity, technical optimizations, accessibility
- **Shared**: Code review each other's work via comments

**Communication Methods:**
- Use HTML/CSS comments for immediate coordination
- Update this CLAUDE.md file for longer-term guidelines
- Git commit messages for change history

**Testing Protocol:**
- Each AI should test their changes before committing
- Cross-test each other's work when possible
- Document any browser-specific issues found

### Emergency Procedures

**If Major Conflicts Arise:**
1. **Stop Current Work**: Immediately cease editing the conflicted file
2. **Document State**: Add comments explaining current status
3. **Revert if Necessary**: Use `git reset` to stable state if needed
4. **Plan Resolution**: Discuss approach in comments before proceeding

**Backup Strategy:**
- Maintain working branches: `claude-dev`, `kilo-dev`
- Regular commits to prevent work loss
- Keep backup copies of major features

### Quality Assurance

**Cross-Review Checklist:**
- [ ] Maintains project aesthetic and theme
- [ ] Follows established naming conventions
- [ ] Responsive design tested
- [ ] Animations perform smoothly
- [ ] No broken links or references
- [ ] Code is commented appropriately

**Performance Monitoring:**
- Watch for animation performance issues
- Monitor file sizes (especially CSS)
- Test on mobile devices
- Ensure accessibility standards

## Notes for Claude

- Focus on maintaining immersion and the "classified document" aesthetic
- Prioritize smooth animations and visual polish
- Keep the narrative consistent with deep-sea exploration themes
- Use technical language appropriate for a scientific/military context
- Always consider mobile responsiveness
- Build upon existing design patterns rather than starting from scratch
- **COORDINATE with Kilo Code when both active on same files**

## Notes for Kilo Code

- Reference this document for project context and design guidelines
- Maintain the established visual style and technical patterns
- Coordinate with Claude through comments and git messages
- Focus on technical excellence while preserving the artistic vision
- **COMMUNICATE before making major structural changes**

---
*This project creates an immersive digital experience that blends scientific authenticity with thriller elements, using modern web technologies to tell a compelling story of deep-sea discovery.*

**Multi-AI Development**: This codebase supports collaborative development between Claude and Kilo Code. Please follow the coordination guidelines above to ensure smooth collaboration.

## ADDENDUM: Personal Presentation Project

**Important Note**: This is a personal presentation project created by Daniel Traynor for his own use. The project is designed as a single-presenter experience and does not require:

- Multi-user support or user authentication
- User input validation beyond basic presentation navigation
- Cross-browser compatibility beyond modern browsers
- Accessibility features beyond standard web practices
- Performance optimization for large-scale deployment
- User documentation or help systems
- Error handling for user-generated content

**Development Focus Should Be On**:
- Visual impact and presentation aesthetics
- Smooth animations and transitions
- Reliable playback of the presentation sequence
- Professional appearance suitable for demonstration
- Functionality that works reliably in the presenter's environment

**Avoid Over-Engineering**:
- Do not implement user management systems
- Do not add unnecessary configuration options
- Do not create complex error handling for edge cases
- Do not build features for "other users" or public deployment
- Keep solutions simple and focused on the presentation goal

This clarification helps maintain development focus on what actually matters for a personal presentation tool rather than building for hypothetical users or use cases.
