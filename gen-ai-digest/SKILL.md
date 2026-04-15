---
name: gen-ai-digest
description: Produces a themed GenAI digest from a curated list of blogs covering the last 48 hours, saved as a dated markdown file on the Desktop. Use only when the user explicitly invokes /gen-ai-digest.
version: 1.0.0
---

# GenAI Digest

Fetch recent posts from a curated blog list, group them by theme, and write a dated markdown digest to `~/Desktop/gen-ai-digest/YYYY-MM-DD.md`.

## Sources

Fetch each of these in turn:

- https://www.oneusefulthing.org/
- https://lucumr.pocoo.org/
- https://simonwillison.net/
- https://worksonmymachine.ai/
- https://blog.fsck.com/
- https://secondthoughts.ai/
- https://www.jonstokes.com/

Only include posts published within the last 48 hours. If a source is unreachable, include a brief note at the bottom of the digest under `## Sources Unavailable`.

## Workflow

1. Fetch all 7 sources and collect posts from the last 48 hours
2. Identify 3–6 themes across the posts (e.g. "AI Agents", "Models & Releases", "Practical Tools", "Policy & Industry")
3. Group posts under themes — a post can appear under only one theme
4. Write the digest file
5. Create the output directory if it doesn't exist: `~/Desktop/gen-ai-digest/`
6. Save as `~/Desktop/gen-ai-digest/YYYY-MM-DD.md` using today's date

## Output Format

```markdown
# GenAI Digest — [Day, Month DD YYYY]

## [Theme Name]

### [Post Title]([source URL])

- **[Descriptive category]:** [Plain-English explanation, 1–2 sentences. Define any technical terms.]
- **[Descriptive category]:** [What this means in practice or why it matters.]
- **[Descriptive category]:** [Broader context or implication.]
- **[Descriptive category]:** [Optional 4th bullet if the post warrants it.]

...repeat for each post in this theme...

## [Next Theme]
...

---
*Sources unavailable (if any):*
- [source name] — could not be reached
```

## Tone rules

- Audience: Analytics Engineer — data-savvy but not a software developer
- Always explain technical jargon in plain English on first use, e.g. "inference (running a model to get a response)"
- Use data/analytics analogies when helpful (e.g. compare a model's context window to a spreadsheet's row limit)
- No hype, no filler phrases like "exciting developments"
- Bullet category labels should be specific and descriptive, not generic (e.g. **What changed:**, **Why this matters for data work:**, **The catch:**, **In plain English:**)
