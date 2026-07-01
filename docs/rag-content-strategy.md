# Repository Content Strategy for Humans + RAG

This repository should remain human-readable first, while also becoming RAG-friendly for future AI use.

## Recommendation

- Keep each post as the canonical source for humans.
- Add lightweight structure so content can be chunked, embedded, retrieved, and reused by AI systems.
- Treat RAG-readiness as a publishing constraint, not a separate content type.

## Suggested principles

1. **One canonical article**
   - Clear title
   - Precise technical claims
   - Stable section headings
   - Explicit conclusions

2. **RAG-friendly structure**
   - Short introduction stating the problem and scope
   - Sections with descriptive headings
   - Concise paragraphs focused on one idea each
   - Lists for decisions, trade-offs, and recommendations
   - Terminology used consistently

3. **Metadata for retrieval**
   Add front matter fields such as:
   - `title`
   - `description`
   - `lang`
   - `topics`
   - `keywords`
   - `abap_objects`
   - `sap_modules`
   - `architecture_tags`
   - `summary`

4. **Chunkable writing style**
   - Avoid references like "as mentioned above" when possible
   - Make each section understandable in isolation
   - Include concrete names for SAP components, transactions, tables, or patterns
   - State assumptions explicitly

5. **Future AI reuse**
   From one post, future tooling should be able to derive:
   - summaries
   - Q&A pairs
   - embeddings
   - semantic search results
   - draft LinkedIn posts
   - agent reference notes

## Practical conclusion

Yes, it makes sense to evolve the repository so it is not only a post collection for humans, but also a clean knowledge base for RAG and downstream AI workflows.

The right approach is:
- human-first reading
- machine-friendly structure
- reusable metadata

## Next repository step

Create or update a contributor guide and post template so every new article follows these rules by default.
