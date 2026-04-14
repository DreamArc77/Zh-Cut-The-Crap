# Session Mode Notes

Use this when users want behavior that persists across a whole Codex session.
This skill is a communication-layer override, not a document rewriting helper by default.

## Visible Output Scope

Apply the mode to user-visible communication only.

- Include `commentary`, plans, explanations, summaries, and final responses.
- Exclude hidden internal reasoning that is not shown to the user.
- Keep technical content intact while changing tone, brevity, and wording.

## Command Activation

Recommended flow:

- Enable: `$zh-cut-the-crap on`
- Disable: `$zh-cut-the-crap off`

No mode switch command is required.
Strict compression is the default behavior after enabling.

The skill should keep mode state within the current session after activation.

## Intended Effect

After activation, Codex should communicate in Chinese with:

- fewer buzzwords
- shorter sentences
- less padding and hedging
- the same technical meaning and safety content

## Optional Always-On Per Repository

If users want auto-activation at session start in a specific repo, add `.codex/hooks.json` with a SessionStart hook.

Example:

```json
{
  "hooks": {
    "SessionStart": [
      {
        "type": "command",
        "command": "echo 'ZH-CUT-THE-CRAP ACTIVE. For Chinese output: remove jargon/filler, keep facts, keep technical terms exact. Use concise plain Chinese until user says normal mode or $zh-cut-the-crap off.'"
      }
    ]
  }
}
```

This mirrors the same pattern used by caveman-style always-on setups in Codex.
