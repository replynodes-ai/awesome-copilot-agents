---
name: url-to-markdown
description: Fetch a public webpage as clean Markdown for GitHub Copilot agent context.
license: MIT
compatibility: Network access only.
metadata:
  author: ReplyNodes
  repository: https://github.com/replynodes/replynodes-agent-skills
  source: https://github.com/replynodes/replynodes-agent-skills/tree/main/skills/url-to-markdown
  docs: https://replynodes.com/markdown-api/
---

# URL to Markdown

Use this skill when an agent needs the readable content of a public webpage as Markdown for summarization, extraction, quoting, or citation.

## Workflow

1. Preserve the exact public URL supplied by the user.
2. Fetch it from the read-only endpoint, replacing `<target>` with the URL target:

   ```bash
   curl -sS https://md.replynodes.com/<target>
   ```

   For example:

   ```bash
   curl -sS https://md.replynodes.com/example.com
   ```

3. Use the returned Markdown as source context and keep the source URL with any cited findings.
4. Do not use this workflow for login-only, private, local, or form-submission pages.

## References

- [Markdown API documentation](https://replynodes.com/markdown-api/)
- [Canonical skill source](https://github.com/replynodes/replynodes-agent-skills/tree/main/skills/url-to-markdown)
