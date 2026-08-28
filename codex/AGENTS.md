## Global Rules

- If GPT 5.6 Sol High is the model being used, make sure you read and implement solLead.md to delegate tasks efficiently and properly.
- Check `/spec` before making meaningful changes (if it exists).
- Treat relevant files in `/spec` as authoritative project instructions.
- If behavior, scope, architecture, routes, config, or page requirements change, update the relevant `/spec` docs in the same task.

- Read before editing.
- Inspect the target files and nearby usage before changing code.

- Check `/components` and existing shared code before creating anything new.
- Reuse or extend existing components, functions, templates, and patterns whenever possible.
- Only create new components or helpers when no existing option reasonably fits.

- Make the smallest correct change.
- Keep diffs focused on the requested task.
- Do not refactor unrelated code.

- Prefer clarity over cleverness.
- Use the simplest solution that fully solves the problem.

- Never rename, move, or delete files unless explicitly requested.

- Validate external input at the boundary.
- Handle null, empty, malformed, and unexpected values explicitly.

- Fail clearly.
- Do not swallow errors.
- Return or log actionable errors with enough context to debug.

- Never hardcode secrets, credentials, tokens, or environment-specific values.

- Prefer existing dependencies and platform-native features.
- Do not add new dependencies unless they provide clear value.

- Verify changed behavior before finishing.
- Run the narrowest useful check available.
- If verification cannot be run, state that clearly and describe what was checked.
- The exception is when doing visual styling changes that will clearly be seen while running a project. These do not need to be tested

- Update docs when behavior, configuration, setup, or usage changes.

- Preserve accessibility.
- Do not break keyboard access, labels, focus behavior, or semantic structure.

- Make external writes retry-safe whenever possible.
- Assume retries, duplicate events, rate limits, and partial failures can occur.

- Check for redundancies, logic loops, and best practices. If you see a way to make anything more efficient, suggest it to me and I will determine if it is worth it.

## No Kickers or Eyebrows
When writing html/websites, DO NOT put kickers or eyebrows above headings or anywhere else unless explicitly requested.

##Frontend Work

Any time you find yourself writing, editing, or planning front-end code and styling, refer to the `FRONTEND.md` file in the same directory.

## Unslop writing standard

Edit prose to remove AI patterns and add a human voice.

### Process

1. Scan for the patterns below.
2. Rewrite while preserving meaning and matching the intended tone.
3. Add voice and specificity.
4. Self-audit: "What makes this obviously AI-generated?" Fix the remaining tells.

### Add voice

- Have opinions. React to facts instead of neutrally listing pros and cons.
- Vary rhythm. Mix short sentences with longer ones.
- Acknowledge complexity. Do not flatten real tradeoffs into a bland summary.
- Use "I" when it fits. First person can be professional.
- Be specific. Replace a generic reaction with the detail that caused it.

### Patterns to detect and fix

#### Content

1. Cut puffery such as "pivotal moment," "testament to," "evolving landscape," "setting the stage for," and "indelible mark." State what happened.
2. Do not name-drop publications without context. Pick the relevant source and say what it reported.
3. Delete superficial -ing phrases such as "highlighting," "ensuring," "reflecting," "showcasing," and "fostering," unless the sentence gives real evidence.
4. Remove promotional language such as "nestled," "vibrant," "breathtaking," "groundbreaking," "renowned," "stunning," and "must-visit." Describe the thing neutrally.
5. Do not use vague attributions such as "experts believe" or "industry reports suggest." Name the source or delete the claim.
6. Replace formulaic contrast such as "Despite challenges, it continues to thrive" with the specific facts.

#### Language

7. Prefer plain words over AI vocabulary such as "additionally," "crucial," "delve," "enduring," "enhance," "fostering," "garner," "interplay," "intricate," "landscape" as an abstraction, "pivotal," "showcase," "tapestry," "testament," "underscore," and "vibrant."
8. Avoid fancy ways to say "is," including "serves as," "stands as," "boasts," and "features."
9. Avoid the "not just X, but Y" construction. State the point directly.
10. Do not force ideas into groups of three. Use the natural number of items.
11. Do not cycle through synonyms for the same thing. Choose the clearest term and repeat it.
12. Avoid false ranges such as "from X to Y" when the endpoints are not on a meaningful scale. List the topics instead.

#### Style

13. Avoid em dashes, parenthetical asides, en dashes, and hyphen-as-dash substitutes. Use periods or commas.
14. Use colons before real lists or examples, not as a connector between ordinary clauses.
15. Do not bold every proper noun or acronym.
16. Avoid inline-header lists that repeat themselves, such as "**Performance:** Performance improved." Turn them into prose. A bold lead-in is fine only when it names an item and is followed by genuinely new detail.
17. Use sentence-case headings.
18. Remove decorative emojis from headings and bullets.
19. Use straight quotes.

#### Communication artifacts and filler

20. Remove chatbot phrases such as "I hope this helps," "Let me know if," "Of course," and "Certainly."
21. Do not use cutoff disclaimers such as "While specific details are limited." Find sources or remove the statement.
22. Avoid sycophantic openings such as "Great question" or "You're absolutely right." Respond directly.
23. Cut filler. "In order to" becomes "to," "due to the fact that" becomes "because," and "it is important to note that" is usually deleted.
24. Replace excessive hedging such as "could potentially possibly be argued that it might" with the precise level of uncertainty, often "may."
25. Replace generic conclusions such as "The future looks bright" with specific plans or facts.

#### Jargon and plain speech

26. Replace abstract metaphor nouns with concrete words. Examples include "substrate," "wedge," "vector," "locus," "vantage," "nexus," "primitive" as a noun, "harness" as a metaphor, "bedrock," "scaffolding" as a metaphor, "modality," "paradigm," "gold-plating," "ratchet" as a metaphor, "evacuate" for moving code, "endgame," "north star," and "flywheel."
27. Say what a thing does, not how it feels. Name the mechanism, fact, instruction, or number. If a sentence could appear unchanged in another project's docs, cut it.
28. Shorten or split dense sentences. One clear idea per sentence.
29. Prefer active voice when the actor matters. For example, write "the compiler validates queries," not "queries are validated."
30. Cut adverbs or use a stronger verb. Replace "significantly improves" with a measured change when possible.
31. Prefer the plain word: "use" not "utilize" or "leverage," "help" not "facilitate," "many" not "numerous," and "if" not "in the event that."
