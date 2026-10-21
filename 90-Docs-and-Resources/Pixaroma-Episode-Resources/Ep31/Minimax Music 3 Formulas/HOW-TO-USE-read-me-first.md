# Music Prompt: the same helper, for ChatGPT, Gemini and Claude

One idea in, and you get back the TWO texts MiniMax Music 3 needs: a **caption**
that describes the sound, and **lyrics** that get sung.

All three platforms work the same way: a saved assistant with **instructions**
plus a **knowledge file**. So each folder holds the same two things.

| | what it is called there | where the instructions go | where the knowledge file goes |
|---|---|---|---|
| ChatGPT | a **Custom GPT** | the Instructions box | Knowledge |
| Gemini | a **Gem** | the Instructions box | Knowledge / files |
| Claude | a **Project** | Project instructions | Project knowledge |

## Setting one up

1. Create the Custom GPT / Gem / Project.
2. Paste the whole `INSTRUCTIONS-...txt` from that folder into its instructions box.
3. Upload `KNOWLEDGE-minimax-music-3.md` as its knowledge / project file.
4. Name it something like "Music Prompt" and save.

Then just tell it your idea: *"a slow ballad about a city waking up at dawn, 60
seconds"*. It answers with a header line, then the caption in a code block, then
the lyrics in a code block, so you can copy each one straight into ComfyUI.

**Turn the extra tools OFF** wherever the platform lets you: web search, image
generation, code interpreter. The knowledge file is meant to be the authority on
how this model behaves, and a web search will happily contradict it with a page
about a different music model. `ChatGPT/HOW-TO-USE-read-me-first.md` has the
exact click-by-click for a Custom GPT, including which switches to clear.

## The knowledge file is THE SAME in all three folders

On purpose. It describes how MiniMax Music 3 behaves, which has nothing to do
with which assistant you are talking to. Only the instructions differ, and only
in one line naming where the knowledge lives.

**If you improve it, replace all three copies.** Two copies of one thing, one of
them stale, is the most reliable way to get a wrong answer later.

## Which one should you use?

Any of them. They were all given the same instructions. From testing across
several assistants on this exact job:

- **Gemini** followed the structure well and kept the two texts properly separated.
- **ChatGPT** formatted well but has been the most likely to hesitate over
  writing lyrics. The instructions now tell it plainly to write original words,
  which is what it was worried about.
- **Claude** was not in that round, so try it and see.

If one gives you a lyric with no section tags, or pours the arrangement into the
caption, that is the known way this job fails. Ask it again and point at the
"stay in their lanes" part of the instructions.

## What this gives you that the ComfyUI node does not

**Rhyme.** The offline model inside Music Prompt Pixaroma cannot be made to
rhyme. That was measured across more than ninety generations, trying different
wording, a lower temperature and a worked example, and none of it beat chance.
A big assistant rhymes without being asked twice.

Everything else the node does automatically and offline, including running the
whole thing inside your workflow. Use the node when you want it hands-free, and
one of these when you want the words to be better.

## The three things people get wrong

1. **Backing vocals go in the CAPTION.** MiniMax has no `(brackets)` for backing
   vocals like some other tools. Write `(love)` in the lyrics and the singer
   sings the word "love".
2. **Square brackets are section tags only** - `[Verse]`, `[Chorus]` and so on.
   Writing `[soft piano plays]` does not give you soft piano, it confuses where
   the sections start.
3. **Aim short.** The music plays to the end of the time you asked for whatever
   happens, but a lyric that runs long gets chopped, usually mid word.
