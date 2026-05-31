Read the daily note from C:\Users\jeryl\OneDrive\Documents\MyVault\Daily Notes\ using today's date in YYYY-MM-DD format as the filename (e.g. 2026-06-01.md). If a specific date is provided in the arguments (e.g. "05-31"), use that date instead (e.g. 2026-05-31.md).

Then do the following:

1. **Scan the vault for existing notes** — list all .md files in C:\Users\jeryl\OneDrive\Documents\MyVault\ (recursively, excluding the Daily Notes folder itself). Collect their filenames (without the .md extension) as the set of linkable note names.

2. **Identify wikilink candidates** — scan the daily note content and find any words or phrases that refer to an existing note from step 1, either:
   - **Exact match** (case-insensitive): wrap directly, e.g. `[[ClaudeCode]]`
   - **Thematic match** (same concept, different wording): use the pipe alias syntax to preserve the original wording, e.g. `[[Room Makeover|room revamp]]`
   
   Do not invent links to notes that don't exist. Only link when you are confident the content is referring to the same subject as the existing note.

3. **Suggest frontmatter tags** — based on the topics covered in the note, propose an updated `tags:` list in the YAML frontmatter. Always keep the existing `daily` tag. Add specific topic tags relevant to the content (e.g. finance, investing, room-setup, claude-code, insurance, health, work).

4. **Show a preview** — display the full proposed updated file content in a code block so the user can review exactly what will change. Clearly call out:
   - Which wikilinks were added and which existing note they point to
   - Which tags were added

5. **Ask for confirmation** — ask the user if they'd like to apply the changes, skip any specific ones, or cancel entirely. Only write to the file after they confirm.
