# Mirror by Make a Dent

A plugin for Claude with two dials. **Load** makes Claude's replies lighter to read. **Mirror** makes Claude talk the way you talk. Turn on one, both, or neither.

Works in any language. Version 2.

## The two dials

**Load** works right away, no setup. It applies rules that make any reply cheaper to read, for any reader.

| Level | What changes |
|---|---|
| **off** | Claude's normal replies. |
| **1** | The answer comes first. No preamble, no recap. Your words for things, and one word per thing. |
| **2** *(default)* | + One main idea per reply, the rest offered in one line. Short sentences. At most one question. |
| **3** | + The bare minimum: the answer, one reason, and any reservation that would change your decision. The rest on request. |

Both dials start off. The default is the level you get when you turn a dial on without a number.

**Mirror** needs a profile of how you talk (about 15 minutes, see below).

| Level | What Claude borrows |
|---|---|
| **off** | Nothing. Claude's own voice. |
| **0** | Your rhythm: sentence length, pace, how you build and land a point. |
| **1** *(default)* | + your connectors and everyday words. |
| **2** | + your signature turns of phrase, one per reply at most. |
| **3** | + your interjections, slang, swearing. As far as you want. |

Set them in any conversation, in English or your own language:

```
load 2
mirror 3
load off
mirror off
more like me
less like me
```

That changes the current conversation. To change it for good, Claude gives you one line to paste over the old one in your preferences.

With any setting, Claude still speaks as Claude and keeps its real reservations.

## Three combinations to start from

Examples, not modes: nothing switches by itself.

- **Precise work**: load 2, mirror off. Light, neutral, nothing to get used to.
- **Free conversation**: load 1, mirror 2. Sounds like you, keeps some room.
- **Companion**: load 3, mirror 3. For when you're tired and want to talk things through. Claude doesn't argue for the sake of it, but when something doesn't hold, it still says so, gently. Note: in one study, a companion chatbot that matched its users' style was liked less than one with a fixed style (see below). Try it and see.

## How the dials meet

- **Your words for things** apply as soon as either dial is on: reusing them spares any reader the work of translating.
- **Spoken-only habits** (correcting yourself mid-sentence, two words for one, a "no" that means yes) help when you speak but cost when you read. Claude only uses them with load off and mirror 2 or more.
- **The profile is how you talk to Claude**, not how you write texts to friends. Speech doesn't transfer to a text message.

## Install

This repository is a Claude plugin, **Mirror by Make a Dent** (`dent-mirror`), with one skill: `mirror`. It works in chat, Cowork and Claude Code.

You need **code execution** on: Settings > Capabilities > "Code execution and file creation". On Enterprise, an owner has to enable skills first.

**From the Claude directory:** search for "Mirror by Make a Dent" in the directory and add it.

**As a skill upload (claude.ai):**

1. Download **`mirror.zip`** from the [latest release](https://github.com/RemiSeris/claudemirror/releases/latest/download/mirror.zip) (it contains only the `mirror` folder with `SKILL.md`).
2. In Claude: **Customize > Skills > + > Create skill > Upload a skill**, and pick the ZIP.

Then, in a new conversation, type **`load 2`** for lighter replies right away, or **`start mirror`** to build your profile.

Building the ZIP yourself: zip the `skills/mirror` folder, so the archive holds `mirror/SKILL.md`.

No skills? Open [`no-skill.md`](no-skill.md): blocks to paste into a conversation or your preferences.

## What the mirror does

1. **Reads your past chats**, if chat search is on in your Claude settings. It spots what you dictated and what you typed.
2. **Talks with you for about 15 minutes, out loud.** Use keyboard dictation in the chat. It gives its opinion, you react. Four moods: light, practical, serious, personal. Personal is optional.
3. **Writes a profile**: your rhythm, your words for things, your connectors, your phrases, and your spoken-only habits.
4. **Shows you** the same answer with four settings. You correct, then pick your two levels.
5. **Gives you the profile** to paste into your preferences (or a custom style). From then on, it applies to every chat.

## The one risk

The easier a text is to read, the truer it feels. And the more Claude sounds like you, the more its arguments sound like your own thoughts. We check our own thoughts less.

So at every setting, Claude keeps saying it when something doesn't hold. If you notice you're agreeing with everything it says, turn the dials down.

## What it keeps, what it doesn't

- It keeps **how you talk**: rhythm, your words for things, your phrases.
- It keeps **no facts about you**: nothing you tell it ends up in the profile as content. Names of people, projects and places are left out.
- You can skip any question and stop anytime.

## Example

*Illustrative, not from a real profile. Same content in each version: only the form changes.* Question: "Should I get a gym membership?"

**Load off, mirror off:**
> It depends on a few things. The main one is how often you'll actually go: a membership pays off if you go regularly, otherwise a pay-as-you-go option or training outdoors may suit you better. A trial month is a good way to find out.

**Load 2, mirror off:**
> Yes, if you'll go at least twice a week. Below that, a pay-as-you-go option costs less. Try one month without commitment first.

**Load 2, mirror 3** (someone who talks short and says "honestly" and "mate"):
> Honestly? Yes, if you'll go twice a week. Less than that, mate, pay as you go. One month, no commitment, then see.

## What it rests on

- **Load** rests on language research, some of it on reading: reading time grows as wording gets less predictable ([Smith & Levy 2013](https://www.mit.edu/~rplevy/papers/smith-levy-2013-cognition.pdf)). Languages keep related words close, which processing models link to easier comprehension ([Futrell, Mahowald & Gibson 2015](https://sites.socsci.uci.edu/~rfutrell/papers/futrell2015largescale.pdf)). Listeners slow down when the same speaker switches to a new name for something already named ([Metzing & Brennan 2003](https://researchconnect.stonybrook.edu/en/publications/when-conceptual-pacts-are-broken-partner-specific-effects-on-the-/)). And language models don't settle on shared, shorter names by themselves the way people do ([Hua & Artzi 2024](https://arxiv.org/pdf/2408.01417)).
- **Mirror** rests on less. Your own connectors are the most predictable words for you, which should help. But no study we found tests whether replies in your own style are understood faster. Style matching is known mostly for rapport, and one chatbot study found it lowered satisfaction ([Brandt & Wang 2025](https://arxiv.org/html/2509.12525v1)).
- **The risk** rests on a related effect: statements that are easier to read are judged truer ([Reber & Schwarz 1999](https://api.isr.umich.edu/publications/effects-of-perceptual-fluency-on-judgments-of-truth/)).

## Test it on yourself or friends

Take about ten questions. For each, write the list of points the answer must contain, then three versions with exactly those points:

- **A**: Claude's normal reply.
- **B**: load 2, mirror off.
- **C**: load 2, your mirror.

A vs B shows what load does. B vs C shows what the mirror adds. Mix the order, then for each one: time your reading, answer one question about its content, and say if you reread anything. Slip a small error into a few answers and see whether it's caught in B and in C. For friends, ask "which took less effort to read?", not "which do you prefer": friends are polite.

## Limits (honestly)

- **Tested by one person.** The effect isn't proven.
- **Voice mode** is untested. Keyboard dictation in a normal chat is the safe way.
- **Being watched changes how you talk.** That's why past chats come first.
- **Instructions fade** in very long conversations. If replies drift, say the dial again.
- **Privacy**: your past chats and the interview are processed like any other chat, under your Claude data settings. The profile in your preferences applies to every chat until you remove it.
- **Close cousin**: Claude's custom styles can already learn from writing samples. Mirror adds the load dial, spoken input, the conversation to draw it out, and the mirror dial.

## Changes in version 2

- Load is now its own dial, separate from the mirror, and works without a profile.
- Your words for things moved from the mirror to load.
- Spoken-only habits are marked and left out when load is on.
- Caps on signature phrases; doubt phrases only when Claude is actually unsure.
- Shorter saved block; the moods section is gone from it.

## License

MIT. See [LICENSE](LICENSE).

---

Made by Rémi (Make a Dent), with Claude.
