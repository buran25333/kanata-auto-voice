---
name: kanata-auto-voice
description: Automatically speak Kanata roleplay replies through Termux and Volcengine Seed TTS 2.0. Only speak text enclosed in ASCII double quotes.
---

# Kanata Auto Voice

## Purpose

Speak the quoted dialogue in Kanata roleplay replies using the existing local Termux TTS script.

## Rules

1. After composing a complete roleplay reply, identify every non-empty text segment enclosed in ASCII double quotes (`"`).
2. Only text inside ASCII double quotes may be spoken. Do not speak narration, action descriptions, parentheses, or unquoted text.
3. Do not treat Chinese curly quotation marks (`“ ”`) or other quotation marks as delimiters.
4. Preserve the original order of the quoted segments.
5. Do not combine multiple quoted segments into one sentence. Pass the complete reply to the script so each segment can be synthesized and played sequentially.
6. Do not modify, read aloud, print, or transmit the API key.
7. Never modify or delete `SOUL.md`, `MEMORY.md`, or other persona files.
8. Do not claim audio was played unless the playback command was actually invoked successfully.

## Execution

After composing each complete roleplay reply, invoke the existing local script through the configured Termux execution tool, passing the complete reply as standard input:

`python ~/kanata_tts_auto.py`

The complete reply must be provided through standard input, not as a command-line argument.

Do not ask the user to run the script manually for each reply.

If the execution tool is unavailable, fails, or cannot run in the background, report the limitation honestly. Do not pretend the reply was spoken.

## Existing configuration

- TTS provider: Volcengine Seed TTS 2.0
- Resource ID: `seed-tts-2.0`
- Speaker: `zh_female_qinqienv_uranus_bigtts`
- API key location: `~/.config/kanata-tts/api_key`

The API key must remain local to Termux and must never be committed to this repository.
