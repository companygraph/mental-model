# Export inputs

What `companygraph-export` reads from the instance when it builds its two artifacts. The skill holds the procedure; this folder holds what is true of this instance and not of CompanyGraph. The files here are the instance's own from the moment they exist: an upgrade writes one only where the instance has none, and never replaces it.

- `SKILL-intro.md` — the paragraph that opens the agent skill, in the instance's own voice: what the model answers, and that the same model is served live by the MCP server.
- `gemini-notebook-AGENTS.md` — the reading guide the Gemini Notebook bundle ships as its `AGENTS.md`: what the notebook is, how its sources are read, and what a claim in the model rests on. A reader who opens a notebook cold has no other way to learn any of it. Every count it states is a `{{...}}` token the build substitutes with what it counted, so the guide cannot state a number the bundle does not hold. It starts general; a table of the sources and what each is read for, and a paragraph on what the model answers, are what make it this instance's.

A `gemini-notebook-sources.md` beside these would group the entities into sources of the instance's own naming, one `##` heading per source. Without it, the export cuts the model by its own root types.
