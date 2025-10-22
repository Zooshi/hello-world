# Claude Code Hooks Setup Instructions

This document explains how to set up hooks to receive beep notifications when Gen AI Research Team tasks complete.

## What are Hooks?

Hooks are shell commands that execute in response to Claude Code events. You can configure hooks to play sounds, send notifications, or perform any custom action when:
- A tool is about to be called (`pre-tool-call`)
- A tool has finished executing (`post-tool-call`)
- User submits a prompt (`user-prompt-submit`)
- And other events

## Setting Up Completion Beep Notifications

To receive a beep notification when research tasks complete, add hooks to your Claude Code settings.

### Option 1: System Beep (Simple)

Add this to your Claude Code settings (typically in `~/.config/claude-code/settings.json` or via settings UI):

```json
{
  "hooks": {
    "post-tool-call": {
      "command": "if [ \"$TOOL_NAME\" = \"Task\" ]; then printf '\\a'; fi",
      "description": "Beep when agent tasks complete"
    }
  }
}
```

This will emit a system beep (`\a`) whenever a Task tool completes (i.e., when an agent finishes).

### Option 2: Audio File (Custom Sound)

For a custom sound file:

```json
{
  "hooks": {
    "post-tool-call": {
      "command": "if [ \"$TOOL_NAME\" = \"Task\" ]; then paplay /usr/share/sounds/freedesktop/stereo/complete.oga 2>/dev/null || aplay /path/to/sound.wav 2>/dev/null || printf '\\a'; fi",
      "description": "Play completion sound when agent tasks complete"
    }
  }
}
```

Replace `/path/to/sound.wav` with your preferred sound file path.

### Option 3: Desktop Notification + Beep (Linux)

For visual notification + beep:

```json
{
  "hooks": {
    "post-tool-call": {
      "command": "if [ \"$TOOL_NAME\" = \"Task\" ]; then notify-send 'Claude Code' 'Agent task completed' 2>/dev/null; printf '\\a'; fi",
      "description": "Show notification and beep when agent tasks complete"
    }
  }
}
```

### Option 4: macOS Notification + Sound

For macOS:

```json
{
  "hooks": {
    "post-tool-call": {
      "command": "if [ \"$TOOL_NAME\" = \"Task\" ]; then osascript -e 'display notification \"Agent task completed\" with title \"Claude Code\"'; afplay /System/Library/Sounds/Glass.aiff; fi",
      "description": "macOS notification and sound when agent tasks complete"
    }
  }
}
```

## Available Hook Variables

When hooks execute, these environment variables are available:

- `$TOOL_NAME` - Name of the tool that was called
- `$TOOL_STATUS` - Status (success/error)
- `$TOOL_OUTPUT` - Tool output (be careful with large outputs)
- And others depending on the hook type

## Notifications for Specific Research Commands

To get notified only when the full research process completes, you can create a more specific hook:

```bash
#!/bin/bash
# Save as ~/.config/claude-code/research-complete-hook.sh

if [ "$TOOL_NAME" = "Task" ] && echo "$TOOL_OUTPUT" | grep -q "Research Coordinator"; then
    notify-send "Gen AI Research Complete" "Your comprehensive research report is ready!"
    printf '\a'
fi
```

Then reference it in settings:

```json
{
  "hooks": {
    "post-tool-call": {
      "command": "~/.config/claude-code/research-complete-hook.sh",
      "description": "Notify when research coordinator completes"
    }
  }
}
```

## Testing Your Hook

After configuring hooks, test them by running:

```bash
/research-market "test topic"
```

You should hear a beep when the market research agent completes.

## Troubleshooting

### No Sound?
1. **Check volume**: Ensure system volume is not muted
2. **Test beep manually**: Run `printf '\a'` in terminal
3. **Check audio server**: Ensure PulseAudio or ALSA is running (Linux)
4. **Test sound file**: Try playing your sound file directly: `aplay /path/to/sound.wav`

### Hook Not Executing?
1. **Check settings syntax**: Ensure JSON is valid
2. **Check permissions**: Ensure hook script is executable (`chmod +x`)
3. **Check Claude Code logs**: Look for hook execution errors
4. **Test command manually**: Copy the hook command and run it in terminal

## Advanced: Progress Notifications

For progress updates during the multi-phase research process, you can create a more sophisticated hook that tracks phase completion:

```bash
#!/bin/bash
# Save as ~/.config/claude-code/research-progress-hook.sh

if [ "$TOOL_NAME" = "Task" ]; then
    if echo "$TOOL_OUTPUT" | grep -q "Market Researcher\|Competitor Analyst\|Target Audience"; then
        notify-send "Research Phase 1" "Discovery phase in progress..." -u low
        printf '\a'
    elif echo "$TOOL_OUTPUT" | grep -q "Product Strategist\|Market Potential"; then
        notify-send "Research Phase 2" "Strategy development in progress..." -u low
        printf '\a'
    elif echo "$TOOL_OUTPUT" | grep -q "Marketing Strategist\|Economic Modeler"; then
        notify-send "Research Phase 3" "Tactical planning in progress..." -u low
        printf '\a'
    elif echo "$TOOL_OUTPUT" | grep -q "Research Coordinator"; then
        notify-send "Research Complete!" "Your comprehensive report is ready." -u critical
        printf '\a\a\a'  # Triple beep for completion
    fi
fi
```

## Security Note

Hooks execute shell commands with your user permissions. Only add hooks you understand and trust. Avoid using untrusted hook scripts.

## Further Reading

For complete documentation on Claude Code hooks, visit:
https://docs.claude.com/claude-code/hooks
