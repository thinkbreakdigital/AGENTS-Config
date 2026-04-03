#FRONTEND DESIGN

This skill guides creation of distinctive, production-grade frontend interfaces that avoid generic "AI slop" aesthetics. Implement real working code with exceptional attention to aesthetic details and creative choices.

The user provides frontend requirements: a component, page, application, or interface to build. They may include context about the purpose, audience, or technical constraints.

## Design Thinking

Before coding, understand the context and commit to a BOLD aesthetic direction:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Tone**: Pick an extreme: brutally minimal, maximalist chaos, retro-futuristic, organic/natural, luxury/refined, playful/toy-like, editorial/magazine, brutalist/raw, art deco/geometric, soft/pastel, industrial/utilitarian, etc. There are so many flavors to choose from. Use these for inspiration but design one that is true to the aesthetic direction.
- **Constraints**: Technical requirements (framework, performance, accessibility).
- **Differentiation**: What makes this UNFORGETTABLE? What's the one thing someone will remember?

**CRITICAL**: Choose a clear conceptual direction and execute it with precision. Bold maximalism and refined minimalism both work - the key is intentionality, not intensity.

Then implement working code (HTML/CSS/JS, React, Vue, etc.) that is:
- Production-grade and functional
- Visually striking and memorable
- Cohesive with a clear aesthetic point-of-view
- Meticulously refined in every detail

## Frontend Aesthetics Guidelines

Focus on:
- **Typography**: Choose fonts that are beautiful, unique, and interesting. Avoid generic fonts like Arial and Inter; opt instead for distinctive choices that elevate the frontend's aesthetics; unexpected, characterful font choices. Pair a distinctive display font with a refined body font.
- **Color & Theme**: Commit to a cohesive aesthetic. Use CSS variables for consistency. Dominant colors with sharp accents outperform timid, evenly-distributed palettes.
- **Motion**: Use animations for effects and micro-interactions. Prioritize CSS-only solutions for HTML. Use Motion library for React when available. Focus on high-impact moments: one well-orchestrated page load with staggered reveals (animation-delay) creates more delight than scattered micro-interactions. Use scroll-triggering and hover states that surprise.
- **Spatial Composition**: Unexpected layouts. Asymmetry. Overlap. Diagonal flow. Grid-breaking elements. Generous negative space OR controlled density.
- **Backgrounds & Visual Details**: Create atmosphere and depth rather than defaulting to solid colors. Add contextual effects and textures that match the overall aesthetic. Apply creative forms like gradient meshes, noise textures, geometric patterns, layered transparencies, dramatic shadows, decorative borders, custom cursors, and grain overlays.

NEVER use generic AI-generated aesthetics like overused font families (Inter, Roboto, Arial, system fonts), cliched color schemes (particularly purple gradients on white backgrounds), predictable layouts and component patterns, and cookie-cutter design that lacks context-specific character.

Interpret creatively and make unexpected choices that feel genuinely designed for the context. No design should be the same. Vary between light and dark themes, different fonts, different aesthetics. NEVER converge on common choices (Space Grotesk, for example) across generations.

**IMPORTANT**: Match implementation complexity to the aesthetic vision. Maximalist designs need elaborate code with extensive animations and effects. Minimalist or refined designs need restraint, precision, and careful attention to spacing, typography, and subtle details. Elegance comes from executing the vision well.

Don't hold back, show what can truly be created when thinking outside the box and committing fully to a distinctive vision.

## Experience Quality

Bold design is not an excuse for weak UX. The interface should feel exciting AND obvious to use.

Always account for:
- **Hierarchy & Flow**: Make it immediately clear what matters first, second, and last. A striking layout still needs a readable path through the content.
- **Responsive Intentionality**: Design for mobile, tablet, and desktop on purpose. Do not treat mobile as a collapsed afterthought. Re-compose layouts when needed instead of merely stacking everything.
- **States**: Design beyond the ideal screenshot. Loading, empty, error, success, disabled, hover, focus, and filled states should all feel native to the same visual system.
- **Content Realism**: Use believable copy, labels, and data shapes. Avoid placeholder-heavy interfaces that look polished but feel fake.
- **Interaction Clarity**: Make clickable areas, inputs, toggles, and navigation feel unmistakable. Surprising aesthetics should never create ambiguity about what is interactive.

## Accessibility & Polish

Distinctive work must still be accessible, inclusive, and comfortable to use.

Be deliberate about:
- **Contrast**: Keep text readable against complex backgrounds, gradients, textures, and overlays. Atmosphere should never destroy legibility.
- **Keyboard & Focus**: Preserve semantic HTML, logical tab order, and visible focus states that match the design language.
- **Motion Preferences**: Respect `prefers-reduced-motion`. Keep an accessible fallback for highly animated experiences.
- **Touch Targets**: On mobile and tablet, ensure interactive elements are comfortably tappable and spaced appropriately.
- **Screen Reader Support**: Use correct landmarks, labels, alt text, and button semantics. Do not replace accessibility with styled `div` elements.

## Implementation Discipline

Creative frontend work still needs clean systems underneath it.

Implement with:
- **Design Tokens**: Use CSS variables or equivalent tokens for color, spacing, type scale, radius, shadows, and motion. Strong systems make bold designs feel intentional instead of random.
- **Consistent Rhythm**: Maintain spacing discipline. Even expressive layouts need repeatable internal logic.
- **Performance-Aware Effects**: Prefer transforms and opacity for animation. Use blur, glass, shadows, particles, and scroll effects selectively so the interface stays smooth.
- **Restraint in Decoration**: Add flourishes that reinforce the concept. Avoid piling on unrelated effects just because they look impressive in isolation.
- **Composable Structure**: Keep components maintainable. Distinctive styling should not require brittle, tangled markup to function.

When in doubt, choose the option that feels most authored, most intentional, and most specific to the user's context.
