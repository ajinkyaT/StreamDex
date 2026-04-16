# Streamdex Source Intake — Connected Context

## When To Use

Use this when a Streamdex-style briefing should be grounded in connected or private sources already available in the host app: broker data, news APIs, repo docs, calendars, internal systems, or search.

This is a fast discovery pass, not a formal data contract. Keep it loose, practical, and best-effort.

## Goal

Collect just enough trusted context to route the request into a normal OpenMontage pipeline, usually `hybrid` first.

## Process

### 1. Identify What Is Available

Look for whatever source channels already exist in the host environment.

Typical buckets:

- broker or portfolio data
- market and news feeds
- repo or docs context
- calendar or task context
- internal search or knowledge tools

Do not block if one bucket is missing. Use what exists.

### 2. Pull The Smallest Useful Slice

Ask for the minimum context needed to tell the story well.

Prefer:

- current positions or holdings over full account dumps
- top movers or watch items over every instrument
- a few strong news items over broad search noise
- a summary of repo or docs changes over raw file dumps

### 3. Package The Context Loosely

Write a compact `external_context` package for downstream stages.

Keep it flexible. Useful keys may include:

- `mode`
- `source_channels`
- `highlights`
- `claims`
- `raw_context_refs`
- `unknowns`
- `as_of`
- `fallback_policy`

This package should help the next stage, not constrain it.

### 4. Preserve Refs, Summarize Aggressively

If the host source provides a usable URI or record id, keep it.

If it does not, store a short note instead of inventing a fake URL.

Good patterns:

- `mcp://broker/positions`
- `codex://repo/diff-summary`
- `internal://calendar/today`

### 5. Keep Moving

If a source is unavailable, incomplete, or noisy:

- note the gap
- keep the best remaining context
- route forward anyway

The point is speed and usefulness, not perfect normalization.

## Suggested Loose Shape

```json
{
  "mode": "host_mcp",
  "source_channels": ["broker", "news", "repo"],
  "as_of": "2026-04-16T09:15:00-04:00",
  "highlights": [
    "Portfolio is tilted toward large-cap tech.",
    "One repo change looks relevant to today's recap."
  ],
  "claims": [
    {
      "text": "Top holding moved higher on the day.",
      "ref": "mcp://broker/positions"
    }
  ],
  "raw_context_refs": [
    "mcp://broker/positions",
    "codex://repo/diff-summary"
  ],
  "unknowns": [
    "No calendar context available yet"
  ],
  "fallback_policy": "use_public_context_for_gaps"
}
```

## Common Pitfalls

- Turning this into a rigid schema
- Blocking because one connected tool is unavailable
- Rewriting host-source data into a fake public URL
- Over-collecting when a small slice is enough
