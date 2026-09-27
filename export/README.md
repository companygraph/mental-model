# Export inputs

What `companygraph-export` reads from the instance when it builds its two artifacts. The skill holds the procedure; this folder holds what is true of this instance and not of CompanyGraph. Both files here are the instance's own from the moment they exist: an upgrade writes one only where the instance has none, and never replaces it.

- `gemini-notebook-AGENTS.md` — the reading guide the Gemini Notebook bundle ships as its `AGENTS.md`: what the notebook is, how its sources are read, and what a claim in the model rests on. A reader who opens a notebook cold has no other way to learn any of it. Every count it states is a `{{...}}` token the build substitutes with what it counted, so the guide cannot state a number the bundle does not hold. It starts general; a table of the sources and what each is read for, and a paragraph on what the model answers, are what make it this instance's.

A `SKILL-intro.md` beside it would open the agent skill in the instance's own voice, and a `gemini-notebook-sources.md` would group the entities into sources of the instance's own naming, one `##` heading per source. Without the second, the export cuts the model by its own root types.
