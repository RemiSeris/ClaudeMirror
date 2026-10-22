# Claude Mirror

A Claude skill that learns how you talk, then talks back to you that way. Easier to read, a bit like talking to yourself. You choose how far it goes.

Works in any language. Version 1.

## What it does

1. **Reads your past chats**, if chat search is on in your Claude settings. It spots what you dictated and what you typed.
2. **Talks with you for about 15 minutes, out loud.** Use keyboard dictation in the chat. It gives its opinion, you react. Four moods: light, practical, serious, personal. Personal is optional.
3. **Writes a profile**: your rhythm, your words, your phrases, what changes with the mood.
4. **Shows you** the same answer at each level. You correct, then pick your level.
5. **Gives you the profile** to paste into your preferences (or a custom style). From then on, it applies to every chat.

## The dial

| Level | What Claude borrows |
|---|---|
| **0 — Rhythm** | Your sentence length, pace, how you build an argument. No words. |
| **1 — Words** *(default)* | + your words for things and your connectors. You stop translating. |
| **2 — Phrases** | + your signature turns of phrase, sparingly. |
| **3 — Full** | + your interjections, slang, swearing. As far as you want. |
| **off** | Claude's normal voice. |

Change it in any conversation (in English or your own language):

```
mirror 2
more like me
less like me
mirror off
```

That changes the current conversation. To change it for good, Claude gives you one line to paste over the old one in your preferences.

At every level, Claude still speaks as Claude, keeps its reservations, and keeps disagreeing when it disagrees.

## Install (claude.ai)

You need **code execution** on: Settings > Capabilities > "Code execution and file creation". On Enterprise, an owner has to enable skills first.

1. Download **`mirror.zip`** from this repo (it contains only the `mirror` folder with `SKILL.md`).
2. In Claude: **Customize > Skills > + > Create skill > Upload a skill**, and pick the ZIP.
3. In a new conversation, type: **`start mirror`** (or "learn how I talk").

Building the ZIP yourself: zip the `mirror` folder, so the archive holds `mirror/SKILL.md`.

No skills? Open [`no-skill.md`](no-skill.md): one message to paste into a conversation, one block to paste into your preferences.

## The one risk

The more Claude sounds like you, the more its arguments sound like your own thoughts. And we check our own thoughts less.

So the skill tells Claude to keep its disagreements at every level. And if you notice you're agreeing with everything it says, turn the dial down.

## What it keeps, what it doesn't

- It keeps **how you talk**: rhythm, the words you use for things, your phrases.
- It keeps **no facts about you**: nothing you tell it ends up in the profile as content. Names of people, projects and places are left out.
- You can skip any question and stop anytime.

## Example

*Illustrative, not from a real profile.* Question: "Should I get a gym membership?"

**Off:**
> It depends on a few things. The main one is how often you'll actually go: a membership pays off if you go regularly, otherwise a pay-as-you-go option or training outdoors may suit you better. A trial month is a good way to find out.

**Level 0** (someone who talks short and leads with the answer):
> Yes, if you'll go at least twice a week. Below that, you're paying to feel guilty. Try a month with no commitment. Still going after three weeks? Take the year.

**Level 3** (same person, who says "honestly" and "mate"):
> Honestly? Yes, if you'll go twice a week. Less than that, mate, you're paying to feel guilty. One month, no commitment. Still going after three weeks, take the year.

## Limits (honestly)

- **Tested by one person.** The effect isn't proven.
- **Short or mirrored?** Part of the effect may just come from shorter answers. Not separated yet.
- **Voice mode** is untested. Keyboard dictation in a normal chat is the safe way.
- **Being watched changes how you talk.** That's why past chats come first.
- **Privacy**: your past chats and the interview are processed like any other chat, under your Claude data settings. The profile in your preferences applies to every chat until you remove it.
- **Close cousin**: Claude's custom styles can already learn from writing samples. Claude Mirror adds spoken input, the conversation to draw it out, the dial, and the moods.

## Try it on friends

Give them the same answer twice, one mirrored, one not, without saying which. Ask: "Which one took less effort to read?" Not "which do you prefer": friends are polite.

## License

MIT. See [LICENSE](LICENSE).

---

Made by Rémi (Make a Dent), with Claude.
