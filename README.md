# Correkt — RP Text Assistant for DragonRealms ~ Coming Soon

Current Information:
| |
|---|---|
| **Version** | v1.2b |
| **Author** | Sekmeht Usho |
| **Release** | Simusoon |

Correkt helps DragonRealms players write immersive, in-character roleplay using AI, so anyone can find their voice in Elanthia regardless of writing ability.

<kbd><a href="screenshots/correkt-ui1.png"><img src="screenshots/correkt-ui1.png" width="350"/></a></kbd>
<kbd><a href="screenshots/correkt-ui2.png"><img src="screenshots/correkt-ui2.png" width="350"/></a></kbd>

*(The name is a blend of "Correct" and "Wrecked" — because sometimes your text is both at the same time.)*

## Why It Exists

DragonRealms is a living world built almost entirely on written communication. How you speak as your character shapes how others experience you, and for many players that pressure is real. Dyslexia, language barriers, anxiety, or simply not having grown up reading fantasy fiction can make roleplay feel intimidating — not because someone lacks imagination or creativity, but because the words don't come easily.

Correkt is a community tool built to change that. It takes what you *mean* to say and helps you say it in a way that feels natural in Elanthia, without changing your voice, your intent, or your character. The goal is confidence and inclusion — keeping your roleplay flowing so you can focus on the story, the people around you, and the world you're all building together.

It does not generate lore, invent actions, or play the game for you. It rewrites *your words*. A player who knows exactly what their character would say but struggles to write it down deserves to be at the table just as much as anyone else.

## What It Does

### Rewriting & Tone
- **Smart default behavior** — with no voice selected, Correkt automatically corrects spelling and grammar only, leaving your text otherwise unchanged
- **Character Voice grid** — choose from nine alignment-based voices (Lawful Good through Chaotic Evil) to shape the tone of your rewrite
- **Custom Tone** — type any free-form tone, style, or persona to override the alignment grid
- **Concise output** — rewrites stay close to the length of your original text, no purple prose
- **Inline directives** — wrap `[instructions]` in square brackets anywhere in your text and the AI will generate content in that spot on the fly
- **AI validation** — every rewrite is checked for meaning before it reaches you; bad or off-topic outputs are automatically retried

### Send Options
- **Say** — with optional target and emote fields
- **Whisper** — with target and visible toggle
- **Yell** — with intensity selector (normal / loud / belt)
- **Chant** — verse-style output, use `\;` to separate lines
- **Sing** — with emote field, use `\;` to separate lines
- **Think** — sends as `think <text>`
- **Send** — sends a direct message to a specific player (`send <player> <text>`)
- **Project** — sends as `project <text>`
- **Use #send** — per-mode toggle that queues the command through Genie's roundtime handler before sending
- **Copy** — copies the rewritten text to clipboard without sending

### Workflow
- **Rewrite** — sends your text to the AI and populates the Rewritten Text box for review
- **Rewrite & Send** — rewrites and sends in one step, no review
- **Send** — sends the rewritten text using the selected send option
- **Reset** — clears input, output, and all selections back to defaults
- **Conv. Mode** — toggles Conversation Mode; type your message and press Enter to rewrite and send immediately, one line at a time, without interrupting your game flow

### Command Line
Type commands directly in the Genie command line without opening the plugin window:

| Command | Description |
|---|---|
| `/correkt` | Open the Correkt plugin window |
| `/correkt <text>` | Rewrite and send `<text>` using your current profile settings |
| `/correkt --reset` | Reset all fields to defaults |
| `/correkt --sendas <mode>` | Change the Send As mode (say, whisper, yell, chant, sing, think, send, project) |
| `/correkt --save` | Save current settings to the active profile |
| `/correkt --help` | Show command reference in the game window |

Status messages from command line operations are echoed to the game window so you always know what changed.

### Profiles
- Save your alignment, tone, custom tone, send mode, theme, and per-mode `#send` preferences per character or situation
- Set a default profile that loads automatically on startup
- New profile dialog pre-fills with your current Genie character name

### UI
- **Dark and light mode** — per-profile theme persistence
- **Always on top** — keep the window above your Genie client
- **Collapsible sections** — Character Voice panel compacts down when not needed
- **Character counts** — live character counts on both Original Text and Rewritten Text fields
- **Status bar** — live feedback including validation pass/fail and retry count after every rewrite

## Requirements

- [Genie Client](https://github.com/GenieClient/Genie4)
- An [OpenAI API key](https://platform.openai.com/api-keys)
- .NET Framework 4.8

## Installation

1. Copy `Correkt.dll` to your Genie `Plugins` folder
2. Launch Genie and load the plugin
3. Click **Settings** and enter your OpenAI API key
4. Type `/correkt` in the Genie command line, or select Correkt from the Plugin list to open the plugin window
5. Get your wordsmithing on

## Settings

- **OpenAI API Key** — stored encoded on disk, never in plain text
- **Model** — defaults to `gpt-4o-mini`, change to any OpenAI chat model you have access to
- **Max Retries** — how many times Correkt will retry a failed validation before surfacing the result (default: 3, max: 10)
