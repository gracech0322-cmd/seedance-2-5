# Seedance 2.5 AI video generation guide: prompts, examples, and API

This repository collects Seedance 2.5 resources for creators and developers: prompt notes, video examples, API tutorials, and workflow tips.

Use it if you want to create AI videos with [Seedance 2.5](https://seegen.ai/seedance-2-5/), write better prompts, or connect Seedance 2.5 to your own app.

## What you'll find

- What is Seedance 2.5
- Seedance 2.5 vs Seedance 2.0
- How to try Seedance 2.5 free
- How to Write a Good Seedance 2.5 prompt
- Seedance 2.5 examples by use case
- Seedance 2.5 API providers comparison
- Seedance 2.5 API integration: a few differences I noticed from Seedance 2.0
- Developer resources

## What is Seedance 2.5?

Seedance 2.5 is the latest AI video generation model in [ByteDance's](https://en.wikipedia.org/wiki/ByteDance) Seedance family.

Compared with Seedance 2.0, it supports longer videos, more reference inputs, better consistency, and more flexible audio workflows.

Seedance 2.5 became available on Dreamina on July 31, 2026. API access opened for developers on August 7, 2026.

Unlike Seedance 2.0, Seedance 2.5 currently only has a Pro version. There is no Fast or Mini version.

Seedance 2.5 supports native output at:

- 480p
- 720p
- 1080p

## Seedance 2.5 vs Seedance 2.0

Seedance 2.5 keeps the main workflows from Seedance 2.0: text-to-video, image-to-video, and reference-based generation.

The main changes are longer video duration, more reference files, and standalone audio reference support.

| Feature | Seedance 2.0 | Seedance 2.5 |
|---|---|---|
| Maximum duration | 15s | 30s |
| Versions | Fast / Pro / Mini | Pro only |
| Image references | Up to 9 | Up to 30 |
| Video references | Up to 3 | Up to 10 |
| Audio references | Up to 3 (requires image/video) | Up to 10 |
| Standalone audio reference | No | Yes |
| Total reference files | Up to 12 | Up to 50 |
| Character consistency | Good | Improved |
| Language support | 8+ languages | 10+ languages |
| Native output | 480p / 720p / 1080p | 480p / 720p / 1080p |

For creators and developers, the practical difference is control. Seedance 2.5 gives you more room to keep characters, scenes, and audio consistent across longer videos.


## How to try Seedance 2.5 free?

It is not always easy to test Seedance 2.5 before paying.

When I checked different Seedance 2.5 platforms, most of them asked for payment before generation. Dreamina is the official Seedance platform, but in my test, it did not always give free Seedance 2.5 access to every user.

I found two platforms that currently let new users try Seedance 2.5 with free credits.

### 1. SeeGen AI

SeeGen AI gives new users free credits after they create an account and join the SeeGen AI Discord community.

Steps:

1. Create a SeeGen AI account
2. Join the SeeGen AI Discord community
3. Receive 200 free credits
4. Use the credits to generate a Seedance 2.5 video

In my test, the free credits were enough for a 480p, 5-second Seedance 2.5 video.

### 2. WaveSpeed AI

WaveSpeed AI gives new users $1 in free credit.

That credit can be used to test Seedance 2.5 generation, including a 480p, 5-second video.

Free credit rules can change, so check each platform before testing.


## How to write a good Seedance 2.5 prompt

A good Seedance 2.5 prompt should describe what happens on screen, not just the style.

Weak prompt:

```text
A cinematic video of a woman in a cafe.
```

Better prompt:

```text
A woman sits alone at a small table in a quiet cafe on a rainy afternoon. She slowly turns a coffee cup with both hands, looks toward the window, and pauses when a taxi passes outside. The camera starts with a medium shot from across the table, then slowly moves closer to her face. Audio includes soft rain, low cafe ambience, and no dialogue.
```

### Basic structure

```text
<Subject> performs <main action> in <scene>.
The visual mood is <style or emotion>.
The camera <shot size, angle, or movement>.
Audio includes <dialogue, ambience, sound effects, or music>.
```

You do not need every line. Keep only what matters for the video.

### 1. Make the action clear

Seedance 2.5 works better when the prompt has a clear start, action, and ending state.

```text
A smart desk lamp sits on a wooden desk beside a notebook. At the start, the lamp is off. A hand enters from the right and presses the power button once. The lamp turns on with warm white light. End state: the lamp remains on, the hand has left the button, and the notebook is still visible.
```

### 2. Give each reference one role

If you upload images, videos, or audio, tell Seedance 2.5 what each file should control.

```text
@Image 1 defines the character's facial features, hairstyle, and clothing. Do not use the image background.
@Image 2 defines the cafe interior, wooden counter, and warm lighting. Do not use the people in the image.
@Video 1 defines the hand movement and pacing of pouring coffee. Do not use the person's identity, clothing, or scene from the video.
```

More references are not always better. Clear roles matter more.

### 3. Keep settings outside the prompt

Do not put duration, resolution, aspect ratio, or frame rate inside the prompt.

Avoid:

```text
Generate a 30-second 1080p video in 16:9.
```

Set these values in the generation page or API parameters instead.

### 4. Use stages for longer videos

For longer videos, split the action into stages.

```text
Stage 1: Opening state: a chef stands behind a kitchen counter with an empty plate in front of him. Primary event: he places a slice of cake onto the plate. End state: the cake is centered on the plate.

Stage 2: Continue from the previous state. Primary event: the chef adds berries and powdered sugar. End state: the decoration is complete and the chef's hands have moved away.

Stage 3: The camera slowly moves closer to the finished dessert. End state: the cake, berries, and powdered sugar remain clearly visible.
```

### 5. Describe emotion through behavior

Instead of only writing "sad" or "tense," describe what the viewer can see.

```text
A woman opens a returned letter at the dining table. When she sees the return mark, her fingers stop moving, her shoulders stay still, and her smile fades. After a slow breath, she turns the envelope face down and looks at the empty chair opposite her.
```

### 6. Write camera and audio clearly

Tie camera movement to a subject and direction.

```text
The camera starts behind the runner at waist height, follows her down the narrow alley, then moves to her left side as she turns into the open street.
```

For audio, separate dialogue, sound effects, ambience, and music:

```text
The man says in natural conversational English: {I found the file.}
<The elevator bell rings once>
(Soft piano music plays in the background)
No subtitles appear on screen.
```

### Quick checklist

Before submitting a Seedance 2.5 prompt, check:

- Is the main subject clear?
- Is the action visible and specific?
- Does each reference file have one clear role?
- Are duration, resolution, and aspect ratio handled outside the prompt?
- If the video is long, is it split into stages?
- If there is camera movement, does it have a target and direction?

## Seedance 2.5 API providers comparison

I checked several Seedance 2.5 API providers in August 2026. The prices below cover generation without video input. Reference video, editing, and extension requests may also charge for the input duration.

| Provider | 480p | 720p | Concurrency | Real-person references | Free trial |
|---|---:|---:|---:|---|---|
| [BytePlus](https://www.byteplus.com/en/activity/seedance2-5) | ~$0.103/s | ~$0.231/s | 3-10 | Approved assets only | No standard trial |
| [SeeGen AI](https://seegen.ai/pricing) | $0.12/s | $0.24/s | 480+ on API plans | Yes, after asset review | 200 credits after joining Discord |
| [Kie AI](https://kie.ai/pricing) | ~$0.14/s | ~$0.315/s | 2-10 | Not confirmed | No |
| [Atlas Cloud](https://www.atlascloud.ai/seedance-2-5) | From $0.134/s | ~$0.30/s | Not disclosed | Yes | No |
| [PiAPI](https://app.piapi.ai/docs/seedance-api/seedance-25) | $0.15/s | $0.35/s | 2-30 | Yes, through its less-restriction model | Trial credits may vary |
| [WaveSpeed AI](https://wavespeed.ai/seedance-2-5-api) | $0.18/s | $0.36/s | 2-300 on common account tiers | Yes, subject to review | $1 for new users |
| [fal](https://fal.ai/models/bytedance/seedance-2.5/reference-to-video) | ~$0.2205/s | ~$0.473/s | 2-40 on self-serve accounts | Restricted or policy-dependent | No Seedance-specific trial |

BytePlus has the lowest base price, but its real-person workflow is more restrictive. Portraits generally need to pass its approved asset process before they can be used as references.

SeeGen AI is slightly more expensive than BytePlus, but it supports reviewed real-person assets and gives new users 200 credits after they join Discord. Its API plans also list more than 480 concurrent tasks.

Atlas Cloud and Kie AI fall in the middle of the price range. Atlas Cloud starts at $0.134 per second, although its public pricing page does not list a separate rate for every resolution. Kie's Seedance 2.5 API is live, but some of its public pages still show older availability information.

PiAPI has both a standard endpoint and a less-restriction endpoint. The less-restriction version costs 10% more:

| PiAPI model | 480p | 720p |
|---|---:|---:|
| `seedance-2.5` | $0.15/s | $0.35/s |
| `seedance-2.5-less-restriction` | $0.165/s | $0.385/s |

WaveSpeed costs more at 480p and 720p, but its paid account tiers allow more concurrent tasks. New users receive $1 in trial credit, which is enough for a short 480p test.

Fal is the most expensive provider in this comparison. It uses token-based billing, so its per-second rates are approximate and depend on the output dimensions.

Prices, trial credits, and concurrency limits can change. Check the provider's pricing page before estimating production costs.

## Seedance 2.5 API integration: a few differences I noticed from Seedance 2.0

I expected the migration from Seedance 2.0 to be mostly a model ID change. The task submission and polling flow is similar, but request routing is stricter.

### Video Edit needs its own mode

Seedance 2.5 may classify an Omni-Reference prompt containing editing instructions as a Video Edit task. Sending a normal ratio and fixed duration can return this error:

```text
`ratio` must be `adaptive`. `duration` must be -1.
```

I now separate ordinary reference generation, editing, and extension before building the request.

With [SeeGen AI](https://seegen.ai/api-docs), the API endpoint stays the same and the model changes from `sd2` to `sd2.5`. Set `mode` to `edit` or `extend`, and place the source video first in `videoUrls`:

```json
{
  "model": "sd2.5",
  "inputs": {
    "mode": "edit",
    "videoUrls": ["asset://source-video"],
    "prompt": "Replace the marked object with a red umbrella",
    "outputResolution": "720p"
  }
}
```

For Video Edit, SeeGen follows the source video's aspect ratio and duration. The source video must be between 4 and 30 seconds. For ordinary reference generation, omit `mode`.

This behavior is also described in the [original Reddit integration note](https://www.reddit.com/r/Seedance_AI/comments/1vmzmr4/seedance_25_api_integration_a_couple_of/).

### Omni-Reference now requires reference files

My Seedance 2.0 integration allowed text-only prompts to use the Omni-Reference route. Seedance 2.5 rejects this because the reference task type is only valid when the request contains an image, video, or audio file.

I now check for reference files first. Text-only requests go to text-to-video, while requests with media use the reference flow.

### Limits and supported inputs have changed

| Feature | Seedance 2.0 | Seedance 2.5 |
|---|---:|---:|
| Maximum duration | 15s | 30s |
| Images | 9 | 30 |
| Videos | 3 | 10 |
| Audio files | 3 | 10 |
| Total references | 12 | 50 |
| Audio-only reference | No | Yes |

SeeGen exposes these full Seedance 2.5 limits. It also supports native 480p, 720p, and 1080p output, with automatic upscaling for 2K and 4K.

Other providers may expose smaller limits. [PiAPI](https://app.piapi.ai/docs/seedance-api/seedance-25), for example, currently allows 9 images, 3 videos, and 3 audio files, and still requires an image or video when audio is included. I keep these limits in each provider adapter instead of using one global Seedance 2.5 configuration.

### Longer requests affect timeouts and billing

A 30-second video usually needs a longer task timeout than a short Seedance 2.0 generation. I also slow the polling interval after the first few checks instead of polling every two seconds until completion.

When reference videos are included, providers may charge for both input and output duration. SeeGen calculates video-input tasks from `output duration + input video duration`, while other providers use their own formulas. I use the final usage value returned by the API whenever possible.

Most of the Seedance 2.0 integration can stay in place. The parts I changed were model selection, request routing, provider limits, timeouts, and billing.

