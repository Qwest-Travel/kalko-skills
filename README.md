# Kalko skills for Claude

Eight free Claude skills for outbound and account research. Each one runs on Claude's own web search,
on purpose kept light (a handful of searches), and every line it writes has a source or says it's unknown.

| Skill | In | Out |
|---|---|---|
| `trigger-map` | your domain | the 5 buying triggers to watch for your product, ranked, with where to see each |
| `job-post-decoder` | a job post | what they're building, build or buy, owner, opening line, open today? |
| `call-wait-skip` | a company | call, wait or skip, with the reason and the source |
| `call-prep` | a company + the person you're meeting | a sourced 1-pager; gaps marked "to discover" |
| `sourced-opener` | a person or company | an opener from one dated fact: DM, email, peer line, 3 follow-ups |
| `event-meetings` | an attendee list | who to meet, ranked, plus requests under the event's limit |
| `filing-plus-job-post` | a US-listed company | its 10-K / 10-Q risks next to its job posts: what it's rebuilding |
| `find-jobs` | your CV + target role | 5 open roles, the exec who owns each, a note and a follow-up |

## Install

You need Claude with web search on. No Kalko account or API key.

**Claude Code.** Install all 8 (needs Node.js 22.20 or newer):

```bash
npx skills add Qwest-Travel/kalko-skills
```

Or one skill: `npx skills add Qwest-Travel/kalko-skills --skill call-wait-skip`. You can also copy a skill folder
into `~/.claude/skills/` by hand.

**Claude.ai (any plan, including Free).**

1. In Settings → Capabilities, turn on "Code execution and file creation".
2. Zip one skill folder, for example `call-wait-skip/`.
3. Go to Customize → Skills → + → Create skill → Upload a skill, and pick the .zip.
4. Turn on web search in the chat, then ask in plain words.

`filing-plus-job-post` works best in Claude Code, because sec.gov sometimes blocks downloads from Claude.ai.

## Rules every skill follows

- Every claim has a URL and a date, or says "unknown" / "to discover".
- Company-level only; public posts and pages only.
- Never invents a quote, a customer or a number.

For the full version (every account in your market, dated sources, call / wait / skip, call prep),
see [Kalko](https://www.kalko.ai/sign-up?utm_source=claude-skills&utm_medium=github&utm_campaign=readme).

License: MIT (see LICENSE).
