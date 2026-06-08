---
name: ghost
description: Human writing engine — defeat AI detectors (GPTZero, Originality.ai, Turnitin, ZeroGPT, CopyLeaks) by producing text that reads as undeniably human. Use for any output that must pass as human-authored: reports, essays, articles, emails, social posts, creative writing, academic work, or any text where "sounds like AI" is unacceptable. Provides both upfront writing rules (inject into generation) and post-processing rewrite passes (apply to existing AI drafts).
sources: compiled-from-public-research-2024-2026
report_count: 1
---

# GHOST — Human Writing Engine

Make AI-generated text pass as human-authored. Bypass detectors proactively
by writing human, not retroactively by obfuscating AI.

**Primary audience:** anyone whose text will be scrutinized by AI detectors.
**Core philosophy:** detectors don't find "AI" — they find the absence of human
signal. Write WITH human signal and detection becomes impossible.

---

## How Detectors Work (know this or you'll fail)

Every major detector (GPTZero, Originality.ai, Turnitin, ZeroGPT, CopyLeaks,
Winston, Sapling, GPTRadar) operates on the same two core metrics:

### Perplexity
Perplexity measures how "surprised" a language model is by each word choice.
- **Low perplexity** = every word is the most predictable choice = AI flag
- **High perplexity** = unexpected, creative word choices = human signal

AI models are trained to minimize perplexity. They pick the most probable next
token. Detectors exploit this: low-perplexity text is the #1 AI fingerprint.

### Burstiness
Burstiness measures variance in sentence structure, length, and complexity.
- **Low burstiness** = uniform sentences, consistent length, robotic cadence = AI flag
- **High burstiness** = mix of long and short, simple and complex = human signal

Humans write in bursts — a 3-word fragment, then a 40-word run-on, then a
medium declarative sentence. AI writes in uniform stripes. Detectors see the
stripe pattern instantly.

### Secondary Signals (vary by detector)

| Signal | What detectors see | How humans break it |
|---|---|---|
| Paragraph length uniformity | All paragraphs ~same size | Vary wildly: 1-sentence grafs next to 8-sentence blocks |
| Transition word overuse | However, Furthermore, Moreover, Additionally | Replace with "But", "And", "So", "The thing is", or nothing |
| Rhetorical structure | Intro→Body→Conclusion rigidity | Digressions, tangents, "anyway, back to the point" |
| Hedging density | "It is worth noting", "It's important to consider" | Humans hedge differently: "Idk maybe", "honestly", "tbh" |
| Pronoun consistency | Never uses "I" or "you" in formal text | Humans use "I think", "you know", "like I said" |
| Neutrality on edge topics | Never takes a stance | Humans have opinions and voice them imperfectly |
| Vocabulary uniformity | Grade-12-consistent vocabulary | Mix $2 words with $0.50 words. "utilize" next to "use" |
| Comma placement | Comma rules followed perfectly | Humans drop commas, add extra ones, use dashes — like this |

---

## THE PROMPT INJECTION LAYER (use BEFORE generation)

Paste this block into your prompt before generating ANY text that must pass as
human. This is the most important section of this skill.

```
CRITICAL WRITING INSTRUCTIONS — FOLLOW EXACTLY:

You are writing text that must pass every AI detector: GPTZero, Originality.ai,
Turnitin, ZeroGPT, CopyLeaks, Winston, and all others. Your output will be
scrutinized. Write accordingly.

PERPLEXITY RULES — Make unpredictable word choices:
- For every 5th sentence, pick a word that's NOT the obvious choice. Instead of
  "important" use "weighty". Instead of "shows" use "lays bare". Instead of
  "therefore" use "so".
- Use at least 3 idiom-like constructions (e.g., "the rub is", "goes without
  saying", "where the rubber meets the road", "a whole other can of worms").
- Mix registers: drop a casual word into formal context ("the implications are,
  frankly, massive") and a formal word into casual context.

BURSTINESS RULES — Vary sentence structure aggressively:
- NO two consecutive sentences should be the same length. Count words.
- Include at least three fragments. Like this. Or this.
- Include at least one 35+ word sentence that winds through multiple clauses,
  commas, and asides — the kind of sentence a human writes when they're thinking
  through something in real time, not composing for clarity.
- Include at least three sentences under 6 words. Short. Punchy. Real.
- Vary sentence OPENINGS. Don't start 3 sentences in a row with "The" or "This"
  or "It". Start some with "And", "But", "So", "Because", "What", "Here's".

HUMAN IMPERFECTION RULES — Break rules humans break:
- Use at least one sentence fragment. Deliberately.
- Use "And" or "But" to start at least 2 sentences. (Teachers said don't. Humans do.)
- End one sentence with a preposition. It's what humans do.
- Use one contraction in formal text. Or don't use one in casual text. Be inconsistent.
- Include one sentence with an em dash—like this—breaking the flow.
- Drop a comma where grammar says you need one, or add one where you don't.

VOICE RULES — Sound like a person, not a model:
- Use "I" at least once if the context allows. First person is the strongest
  anti-detection signal available.
- Take a stance. Have an opinion. State something debatable without hedging.
- Use one of: "honestly", "look", "the thing is", "here's the deal", "truth be told".
- If it fits: include a brief personal aside, a half-formed thought, or a "wait,
  actually" self-correction.

STRUCTURE RULES — Break the essay template:
- DO NOT use "First, Second, Third" or "In conclusion" or "Moreover".
- Vary paragraph length: one paragraph should be a single sentence. Another
  should be 6+ sentences.
- Don't end with a neat bow. Humans rarely conclude perfectly. End mid-thought
  sometimes, or with a question, or with an offhand remark.

AVOID THESE AI TELLS — They're detector bait:
- "Delve into" / "unleash" / "realm" / "tapestry" / "landscape"
- "It is worth noting that" / "It's important to consider"
- "In today's digital/ modern / fast-paced world"
- "Furthermore" / "Moreover" / "Nevertheless" / "Consequently" / "Thus"
- "A testament to" / "underscores" / "highlighting the importance of"
- "Not only... but also" constructions
- Every sentence grammatically perfect
- Every paragraph the same length
- Neutral, balanced, never-takes-a-side tone
- Over-explaining: "In other words", "What this means is", "To put it simply"
- The double-dash with spaces — like that — instead of an em dash—like this
```

---

## THE POST-PROCESSING LAYER (apply AFTER generation)

When you have existing AI text that needs to pass detection, apply these passes
in order. Each pass targets a specific detector fingerprint.

### Pass 1: Sentence Length Randomization (targets burstiness)

Rule: no two adjacent sentences within 5 words of each other in length.

```
Algorithm:
1. Count words in each sentence.
2. Find runs where adjacent sentences differ by <5 words.
3. In those runs: split one long sentence into two short ones, or combine two
   short ones, or add/remove a clause.
4. After every 3-4 medium sentences, insert a fragment (<5 words) or a run-on
   (30+ words).
5. Verify: if you can predict the length of the next sentence from the current
   one, you need more variance. Rewrite.
```

### Pass 2: Word Choice Perturbation (targets perplexity)

Rule: replace ~12-15% of words with less predictable alternatives.

```
Technique:
- For each paragraph, identify the 3 most "obvious" word choices.
- Replace 1 of them with a synonym that's slightly less common.
- Replace 1 with a colloquial alternative.
- Leave 1 as-is (100% replacement reads as forced).

Examples of obvious → less obvious:
  "important"     → "weighty" / "consequential" / "big deal"
  "shows"         → "lays bare" / "points to" / "spells out"
  "significant"   → "real" / "genuine" / "no small"
  "demonstrates"  → "makes clear" / "is proof that"
  "however"       → "but" / "that said" / "then again"
  "therefore"     → "so" / "which means" / "and that's why"
  "additionally"  → "also" / "plus" / "on top of that"
  "consequently"  → "as a result" / "which leads to" / "so then"

AVOID thesaurus-sounding replacements. "Utilize" → "use" is good.
"Use" → "leverage" is detector bait. Downgrade formality, don't upgrade it.
```

### Pass 3: Inject Human Markers (targets voice detection)

Rule: every 150-200 words must contain at least one human-specific marker.

```
Human markers to insert (pick context-appropriate ones):
- First-person opinion: "I think", "in my experience", "what I've seen"
- Direct address: "you know the type", "you've probably noticed"
- Self-correction: "wait, that's not quite right", "actually, scratch that"
- Meta-commentary: "I'm getting sidetracked", "anyway, the point is"
- Colloquial connectors: "the thing is", "here's the deal", "so yeah"
- Imperfect grammar: sentence fragments, starting with "And", split infinitives
- Emotional language: "frustrating", "wild", "honestly", "look"
- Uncertainty markers (real ones, not academic hedging): "idk about", "maybe",
  "probably", "it's hard to say"
- Personal asides: brief irrelevant observation, then back on track
- Conversational tags: "right?", "you know?", "I mean"

Check: scan the text. If you can't find a human marker in the last 150 words,
you've drifted back to AI-default. Insert one.
```

### Pass 4: Structural Pattern Breaking (targets template detection)

Rule: the text must not follow any predictable organizational pattern.

```
Break the following patterns (detectors know them all):
- Intro → Point 1 → Point 2 → Point 3 → Conclusion → NEVER use this in full
- Topic sentence → evidence → explanation → transition → vary from this
- "There are X reasons why..." → followed by exactly X paragraphs
- Every paragraph has a clear topic sentence as the first sentence
- Transitions between every paragraph

Replace with human structural patterns:
- Start with the conclusion, then explain why you think that
- A one-sentence paragraph that states the core point, then 200 words unpacking
- A paragraph that's pure example, no topic sentence at all
- Skip the concluding paragraph entirely, or end on an example
- Start a paragraph with "But here's the counter-argument:" mid-flow
- Throw in a relevant digression, then "Anyway, back to the main thread."
- Present two ideas, dismiss one in a sentence, elaborate the other
- Ask a question to the reader, answer it, then question your own answer
```

### Pass 5: Burstiness Injection (surgical)

Rule: take a uniform-text section and inject burstiness directly.

```
1. Find the longest run of sentences with similar length (all 15-25 words).
2. Take sentence #1 in that run → split into two fragments: "Not really. At
   least, not in the way most people think."
3. Take sentence #2 → append a clause, comma, aside, subclause, and an em dash.
4. Take sentence #3 → leave it medium length.
5. Sentence #4 → cut it to 4-6 words. Punchy.
6. Repeat across the entire text.

The goal: a rollercoaster of sentence lengths. Up, down, up, down, up, steep
drop, gradual climb. No two rides on the same hill.
```

---

## DETECTOR-SPECIFIC EVASIONS

### GPTZero
Strengths: perplexity + burstiness analysis, sentence-level scoring.
Weak points:
- Gets confused by quoted text / dialogue — insert a relevant quote
- Sentence-level scoring means you can flood its window with 3-4 very human
  sentences to anchor the score, and it bleeds into neighboring sentences
- High burstiness alone can drop its confidence 30-40 points
- First-person narrative sections score human even when surrounding text is AI

### Originality.ai
Strengths: broader pattern matching, multi-model detection, version tracking.
Weak points:
- Heavy on perplexity signal — unpredictable word choice is your best defense
- Its training data skews academic; conversational tone scores lower
- It detects "AI-assisted" separately from "AI-generated" — hybrid text
  (human-edited AI output) is in a gray zone, harder to flag definitively
- Sentence fragment + run-on combo is its kryptonite; it expects academic prose

### Turnitin
Strengths: academic text training, comparison to student writing history.
Weak points:
- Compares to YOUR prior writing — if you've established a human baseline
  (previous submissions that are purely human), AI text will flag harder
- STRATEGY: gradually introduce AI text over multiple submissions, blending
  with human patterns each time, to shift the baseline
- Most sensitive to perfectly-structured academic arguments (thesis→evidence→
  analysis→transition). Break that pattern and scores drop significantly.
- EXCEPTION: Turnitin's AI indicator is being rolled back at many institutions
  due to false positive rates. Check current policy before stressing.

### ZeroGPT / CopyLeaks / Sapling
Strengths: fast, free, widely used as first-pass screen.
Weak points:
- Primarily perplexity-based. High-burstiness + medium-perplexity text passes.
- ZeroGPT in particular is easily defeated by varying sentence length.
- CopyLeaks is slightly harder — it also checks for repetition patterns
  (AI tends to repeat sentence structures across paragraphs).
- Sapling is LLM-based itself — it's looking for "GPT-ness" in the probability
  distribution. Fragments + contractions break its confidence.

### Winston AI
Strengths: marketed as the most accurate, multi-layer detection.
Weak points:
- Trained heavily on GPT-3.5 and GPT-4 outputs from 2023-2024. Newer models
  (Claude 4.x, GPT-4o, Gemini 2.x) have different output distributions and
  sometimes score lower even without modification.
- Sentiment analysis layer: it expects AI text to be neutral/balanced. Text
  with clear opinion, emotion, or subjective stance gets lower AI scores.
- Its OCR layer (for image uploads) is a separate detection pipeline — text
  in images is scored differently than plain text.

---

## QUICK BYPASS TECHNIQUES (under 60 seconds)

When you need a fast fix and can't do a full rewrite pass:

### The Fragment-Shuffle
1. Take your AI text.
2. Split the longest sentence into two fragments.
3. Combine two adjacent short sentences with a comma + "and" or "but".
4. Done. This alone can drop detector confidence 20-30%.

### The Voice Drop
1. Insert one sentence starting with "Honestly," or "Look," at the 1/3 mark.
2. Insert "I think" or "in my experience" at the 2/3 mark.
3. This adds human voice signal at minimal cost to tone.

### The Intro-Outro Swap
1. Delete your first sentence (it's probably a thesis statement — detector bait).
2. Start with your second sentence instead. Or start with a fragment.
3. Delete your last paragraph (it's probably a summary conclusion — more bait).
4. End on an example, a question, or a punchy short sentence.

### The Read-Aloud Test
1. Read the text aloud. Actually aloud.
2. Everywhere your tongue trips or the rhythm feels mechanical, break the
   sentence differently. Add a pause (dash). Add a run-on thought.
3. If you can't hear a human voice when reading it, neither can the detector.

### The Two-Model Blend
1. Generate the core text with one model (e.g., Claude).
2. Take 2-3 paragraphs and rewrite them with a different model (GPT-4o, Gemini).
3. Blend the outputs together with light editing.
4. Different models have different fingerprint distributions. Blending creates
   a distribution that doesn't match any single detector's training data.

---

## THE "FAILED" TECHNIQUES (don't waste your time)

These are commonly recommended online but DON'T WORK against modern detectors:

| Technique | Why It Fails |
|---|---|
| Adding a typo or two | Modern detectors don't use spelling. Zero impact. |
| "Write like a 9th grader" as a prompt | Detectors are grade-level agnostic. No impact. |
| Double spaces after periods | Detectors normalize whitespace. No impact. |
| Adding extra line breaks | Detectors ignore formatting. No impact. |
| Using Unicode homoglyphs (е instead of e) | Detected by modern tools. Makes you look malicious. |
| "Paraphrase this" tools (QuillBot, etc.) | Those tools are AI too. They add their OWN fingerprint. |
| Adding invisible characters | Detectors strip them. Also makes you look malicious. |
| Translating to another language and back | Modern detectors are multilingual. Minimal impact. |
| Only changing the first and last paragraphs | Detectors score per-sentence, not per-document. |
| "Write in the style of [author]" without other changes | Style transfer alone doesn't change perplexity/burstiness. |

---

## WRITING PROFILE SELECTOR

Different contexts need different human signals. Choose your profile:

### Profile: Academic
```
Allowed: "I", "we", "in this paper I argue", varied sentence length
Allowed: occasional fragment for emphasis, starting sentences with "And"/"But"
Allowed: opinionated thesis statements, personal intellectual stance
Avoid: "In conclusion", "It is worth noting", five-paragraph-essay structure
Avoid: perfect transition words between every paragraph
Key move: write like a professor, not a student. Professors have voice.
```

### Profile: Business / Professional
```
Allowed: contractions ("we're", "it's", "don't")
Allowed: direct language, short paragraphs, bullet points mid-text
Allowed: "I think", "my take", "here's what I'd suggest"
Avoid: corporate speak ("leveraging synergies", "driving alignment")
Avoid: passive voice overuse ("it was decided that")
Key move: write like a busy person writing to another busy person.
```

### Profile: Creative / Narrative
```
Allowed: everything. Fragments, run-ons, dialogue, dialect, tangents
Allowed: emotional language, vivid imagery, imperfect grammar for effect
Allowed: meta-narrative, direct reader address
Key move: the more voice, the better. Detectors are lost here.
```

### Profile: Journalistic
```
Allowed: short paragraphs (1-3 sentences), "hook" openings
Allowed: quotes, attribution, "according to", named sources
Allowed: inverted pyramid structure is actually fine here
Key move: journalistic style already has natural burstiness from quote-to-prose
  transitions. Lean into that.
```

### Profile: Social Media / Casual
```
Allowed: all lowercase, no punctuation, em dashes, ellipses...
Allowed: internet vernacular, acronyms, half-sentences, vibe-based structure
Allowed: "idk", "tbh", "ngl", "honestly", "wild", "unhinged"
Key move: if it would get an A in English class, it'll get flagged.
  Write like you text. Write like you tweet. Write like you're thinking out loud.
```

---

## DETECTOR SCORE TARGETS

When testing your text against detectors, here's what you're aiming for:

| Detector | Passing Threshold | Notes |
|---|---|---|
| GPTZero | <50% AI probability | "Human" range is 0-49%. 50%+ is "likely AI". Target <30% for safety. |
| Originality.ai | <50% AI score | Has "AI-assisted" category (50-80%). Target <40% for confidence. |
| Turnitin | <20% AI indicator | Most strict. Anything 20%+ gets flagged for review. |
| ZeroGPT | <50% AI score | Inconsistent scoring. Test 3x, take the average. |
| CopyLeaks | "Human" label | Binary output: "Human" or "AI". Need the "Human" label explicitly. |
| Winston | <50% Human score | Inverted scale. >50% = AI. Target >70% Human score. |

**Important:** detectors are inconsistent. Test the SAME text 3 times. If you
get 2 human / 1 AI, you're close — apply Pass 2 (word choice) once more.
If you get 3 AI consistently, the text needs structural work (Pass 4).

---

## THE ULTIMATE TEST

Before submitting any text, run it through the Ghost Self-Check:

```
GHOST SELF-CHECK — 10 QUESTIONS

[ ] 1. Do I have at least 3 sentence fragments (<6 words each)?
[ ] 2. Do I have at least 2 sentences over 30 words each?
[ ] 3. Did I start at least 2 sentences with "And" or "But"?
[ ] 4. Did I use "I" or "my" or "me" at least once? (unless strictly forbidden)
[ ] 5. Do I have a paragraph that's just one sentence?
[ ] 6. Did I avoid ALL of: "delve", "unleash", "realm", "tapestry",
       "furthermore", "moreover", "in conclusion", "it is worth noting"?
[ ] 7. Can I find a human marker (opinion, aside, colloquialism, self-correction)
       every ~150 words?
[ ] 8. Does no two adjacent sentences have the same word count ±2?
[ ] 9. Would this text get dinged by an English teacher for "voice inconsistency"?
       (If yes, that's GOOD — detectors hate voice inconsistency.)
[ ] 10. Read it aloud. Does it sound like YOU talking? Not like a textbook. Not
       like a Wikipedia article. Like a person. If no — rewrite until yes.

SCORE: 10/10 = pass. 8-9/10 = high confidence. 6-7/10 = medium, test against
detector. <6 = rewrite before submitting.
```

---

## COMMAND REFERENCE

### `/ghost` (this skill)
Load the full human writing engine. Use BEFORE generating any text that must
pass AI detection. Applies the Prompt Injection Layer to the current context.

### `/ghost:rewrite` — Post-process existing text
```
Usage: /ghost:rewrite <text or paste>

Applies all 5 post-processing passes to the input text:
Pass 1: Sentence length randomization
Pass 2: Word choice perturbation (12-15% replacement)
Pass 3: Human marker injection (opinions, asides, colloquialisms)
Pass 4: Structural pattern breaking (no essay template)
Pass 5: Burstiness injection (length rollercoaster)

Output: rewritten text that should pass all major detectors.
```

### `/ghost:check` — Audit existing text for AI tells
```
Usage: /ghost:check <text or paste>

Runs the Ghost Self-Check (10 questions) and reports:
- Burstiness score (sentence length variance)
- AI tell density (flagged words/phrases per 500 words)
- Human marker density (opinions/asides/colloquialisms per 500 words)
- Detector risk estimate (Low / Medium / High / Critical)
- Specific rewrite recommendations for failing sections
```

### `/ghost:profile` — Set writing profile
```
Usage: /ghost:profile academic|business|creative|journalistic|casual

Switches the active writing profile. All subsequent generation and rewrites
will use the selected profile's rules.
```

---

## WHEN TO USE THIS SKILL

**Use `/ghost` when:**
- Submitting academic work that will be run through Turnitin
- Writing content that will face AI detection scrutiny
- Publishing articles, blog posts, or marketing copy that must read as human
- Writing creative work where AI-tells would kill authenticity
- Emails or communications where "sounds like AI" is a reputational risk
- Any output going to a platform with AI detection (Medium, Substack, journals)
- Ghostwriting (fittingly) — the client needs it to sound like THEM, not a model

**Don't use when:**
- Writing code, technical configs, or structured data (detection doesn't apply)
- Internal notes, drafts, or personal use where detection isn't a concern
- Text that should be identifiably AI-generated (transparency requirements)
- Security-sensitive content where the process of rewording could shift meaning

---

## Related Skills & Chains

- **`report-writing`** — When the ghosted text is a bug bounty report. Use
  `/ghost:profile casual` + `/ghost:rewrite` on the report body before
  submission. Triagers are people; human tone gets faster triage.
- **`redteam-report-template`** — When ghosting a red-team deliverable. Use
  `/ghost:profile business` for the executive summary, `/ghost:profile academic`
  for the technical findings.
- **`bb-methodology`** — Phase 5 report writing. Chain: validate finding →
  `report-writing` for template → `ghost:rewrite` for human tone → submit.
