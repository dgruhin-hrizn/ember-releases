# Settings: Voice

Every setting in Settings › Voice: type, default, values and what it does.

These settings are in **Settings › Voice** (and in your `settings.json`).

### `ember.profile.name`

Your name, for Ember's spoken lines ("David, …"). Empty: Ember offers one from git or this computer's account the first time it speaks.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.roles.stt`

The transcription endpoint and model for talking back (Settings › Voice): `{ endpoint, model }`.

- **Type:** object or null
- **Default:** `null`
- **Scope:** Application (all windows and profiles)

### `ember.roles.tts`

The speech endpoint and model for Ember's voice (Settings › Voice): `{ endpoint, model }`. Without one, macOS speaks with its British female voice.

- **Type:** object or null
- **Default:** `null`
- **Scope:** Application (all windows and profiles)

### `ember.voice.accuracy`

How accurate talking back is on macOS: Apple's on-device words as they are (Fast), or polished by your transcription endpoint at the pause (Best).

- **Type:** one of the values below
- **Default:** `"auto"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"auto"` | Best when your transcription endpoint runs on this computer, else Fast |
| `"fast"` | Apple's words as they are: no wait at the end |
| `"best"` | Apple shows your words live; at the pause the recording goes to your transcription endpoint, which polishes it before it lands |

### `ember.voice.appleServer`

Let Apple's servers recognise what you say, with the chat's words it's told to expect (more accurate for some languages and accents, and works for a language that isn't downloaded). Off: your voice never goes to Apple's servers.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.voice.bonfire`

Speak Bonfire's news: a to-do needs you, the run needs you to finish it, the run is done.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.voice.done`

Speak when a chat finishes its turn.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.voice.enabled`

Ember says out loud when a chat or Bonfire needs you ("David, the chat “Fix login” is waiting for your approval."). The lines are filled in by Ember — no model is asked, and nothing is sent to Claude.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.voice.language`

The language you talk in (`en`, `en-GB`, `de`…). Empty: this computer's language.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.voice.listenWith`

What turns your words into text while you talk back.

- **Type:** one of the values below
- **Default:** `"auto"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"auto"` | Apple's speech recognition on macOS, else your transcription endpoint |
| `"apple"` | Apple's speech recognition on this Mac (macOS only) |
| `"endpoint"` | Your transcription endpoint (Settings › Voice › Transcription) |

### `ember.voice.muted`

Mute Ember's voice: nothing is spoken, in any window or on your phones, until you unmute. Your other voice settings stay as they are; the notifications and talking back still work. The status bar's speaker (shown while voice is on) and **Ember: Mute / Unmute Ember's Voice** toggle it.

- **Type:** boolean
- **Default:** `false`
- **Scope:** Application (all windows and profiles)

### `ember.voice.needs`

Speak when a chat needs you: an approval, a question, a sign-in, a chat that stopped answering.

- **Type:** boolean
- **Default:** `true`
- **Scope:** Application (all windows and profiles)

### `ember.voice.pauseMs`

How long a pause (in milliseconds) ends what you're saying.

- **Type:** number
- **Default:** `1200`
- **Range:** 500 to 4000
- **Scope:** Application (all windows and profiles)

### `ember.voice.pronunciations`

How Ember says a written word out loud: the word as written → how to say it, for example `{ "nginx": "engine x", "kubectl": "cube control" }`. Whole words in any case, also in a possessive (`nginx's`) or a hyphenated name (`nginx-proxy` is said "engine x proxy"); never inside another word. Only what is spoken changes, never what is shown. A repository can carry its own in `.vscode/settings.json`, so the team gets them by opening it (up to 100 words, and none until you trust the folder); yours win for the same word. Edit yours in Settings › Voice › Pronunciations.

- **Type:** object
- **Default:** `{}`
- **Scope:** User or workspace

### `ember.voice.quietFrom`

Quiet hours start (`HH:MM`, this computer's clock). Empty: no quiet hours.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.voice.quietTo`

Quiet hours end (`HH:MM`).

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.voice.readReplies`

Read Claude's replies aloud: the first paragraph or summary line of what Claude wrote (never code or tables). Nothing more is asked of the model.

- **Type:** one of the values below
- **Default:** `"off"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"off"` | Never read replies aloud |
| `"chosen"` | Read replies aloud in the chats you turn it on for (the speaker in the composer) |
| `"always"` | Read every reply aloud |

### `ember.voice.talkMode`

What happens when you stop talking: send it after a short countdown, or leave it in the composer.

- **Type:** one of the values below
- **Default:** `"send"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"send"` | When you pause, a short countdown runs, then what you said is sent (speak again to keep going; Esc or a click cancels) |
| `"dictate"` | When you pause, what you said waits in the composer for you to check and send |

### `ember.voice.voice`

The voice: a voice of the speech endpoint (`bf_emma`), or a macOS voice as `say:<name>`. Empty: British female — Kokoro's Emma, else the endpoint's British female voice, else macOS's Serena or Kate.

- **Type:** string
- **Default:** empty
- **Scope:** Application (all windows and profiles)

### `ember.voice.volume`

How loud Ember speaks (0–100).

- **Type:** number
- **Default:** `80`
- **Range:** 0 to 100
- **Scope:** Application (all windows and profiles)

### `ember.voice.when`

When Ember speaks.

- **Type:** one of the values below
- **Default:** `"unfocused"`
- **Scope:** Application (all windows and profiles)

| Value | Meaning |
|---|---|
| `"unfocused"` | Only while Ember isn't the app you're using |
| `"always"` | Always, except about the chat you're looking at |

---

[All documentation](../README.md)
