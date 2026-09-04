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
| Native output | 480p / 720p / 1080p / 4K | 480p / 720p / 1080p |

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

## Seedance 2.5 prompt examples by use case
Browse examples across cinematic shots, action and sports, stories and dialogue, product ads, music and dance, nature and travel, and visual effects. Each example includes the final video, references, prompt, and source so you can see how the instructions translate into motion.

### Cinematic Shots

#### FPV Drone Flight Through a Mountain Valley

A single-take flight that climbs beside a waterfall, dives toward a river, passes over a village, and flies through a mountain gap.

**Target duration:** 25 seconds. Set the duration in the generation controls.

| Final Video | References | Prompt | Source |
| --- | --- | --- | --- |
| [Watch video](https://example.com/fpv-drone-result.mp4) | [Reference image](https://example.com/fpv-drone-reference.jpg)<br>[Reference video](https://example.com/fpv-drone-reference.mp4) | **Goal:** A first-person FPV racing-drone flight through a mountain valley in one continuous, uncut take. Cinematic live-action look, clear blue skies, natural sunlight, and realistic atmospheric perspective.<br><br>**Camera:** Face the direction of travel, pitching with climbs and dives and banking slightly through turns. Convey speed through passing terrain and subtle inertial sway.<br><br>**Route:** Lower-left green hillside → waterfall crest → waterfall base → stone village → V-shaped mountain gap → open valley beyond. Follow this order without backtracking.<br><br>**Climb:** Start low over the green hillside in the lower-left part of the valley. Accelerate uphill toward the large waterfall on the left. Climb beside its left cliff wall, then curve toward the crest. Pitch downward to reveal the upstream stream and the waterfall's edge.<br><br>**Dive:** Pass the crest and pitch into a steep forward dive alongside the cliff beside the waterfall. Skim the outer edge of the spray without entering the water curtain or dense mist. Pull out just above the river at the base.<br><br>**Village pass:** Bank right and follow the winding river in smooth curves. Fly fast and low over the rooftops of the stone village in the middle of the valley.<br><br>**Mountain gap:** Continue farther right along the river valley toward the two tallest distant peaks. Fly through the exact center of the V-shaped gap between them. Emerge into the open valley and settle into smooth forward flight.<br><br>**Continuity:** Keep terrain, weather, and sunlight consistent. Connect all movements without cuts. No backward flight, retracing, aimless circling, hovering, black frames, time jumps, or sped-up jump cuts. Do not display text, route lines, labels, or numbers. | Volcengine |

### Action & Sports

#### Zane's Electric Superhero Origin

A ten-panel superhero story follows Zane from a lightning strike to his first rescue, with cartoon action and a soundscape for each scene.

<!-- Replace the video and storyboard placeholder links with your actual URLs. The prompt below is reproduced as provided. -->

| Final Video | References | Prompt | Source |
| --- | --- | --- | --- |
| [Watch video](https://example.com/zane-superhero-result.mp4) | [10-panel storyboard](https://example.com/zane-superhero-storyboard.jpg) | CONTENT ADVISORY: Family friendly Pixar superhero origin story. Stylized cartoon action only. Safe for all audiences. Similar to The Incredibles and Spider-Man Into the Spider-Verse.<br><br>This storyboard has 10 numbered panels. Animate each panel as a separate video clip in sequence. Elements On — include realistic ambient sounds for each panel.<br><br>**Panel 1:** ZANE walks down rainy city street, camera slowly pushes in from behind, rain falling softly, city sounds — traffic, distant music, wet footsteps on pavement, warm orange city glow reflecting in puddles, completely ordinary peaceful moment. 3 second hold. Eye level wide shot slow dolly in. Sound: rain, city traffic, footsteps.<br><br>**Panel 2:** Camera locks as storm clouds spiral overhead impossibly fast, green purple lightning crackling between clouds, ZANE looks up slowly jaw dropping, crowd begins running in panic around him, wind picking up dramatically, ZANE completely still fascinated. 3 second hold. Low angle looking up. Sound: thunder building, wind howling, crowd panic.<br><br>**Panel 3:** Massive lightning bolt strikes ZANE, camera freeze frame at impact, electric cocoon wraps entire body, every raindrop frozen mid-air, city goes dark from power surge, shockwave ripples outward from impact point, complete silence for 1 second then massive thunderclap. Extreme wide shot maximum VFX slow motion. Sound: deafening thunderclap, electrical crackling, city power cutting out.<br><br>**Panel 4:** ZANE on hands and knees, smoke rising from hoodie, looks at own hands crackling with blue electricity, rain hissing on glowing skin, eyes wide with shock and wonder. Extremely slow push in toward crackling hands. Sound: electricity crackling, rain hissing on hot skin, ZANE breathing heavily.<br><br>**Panel 5:** Electricity flows across entire body like second skin, eyes glow solid blue, rain evaporating before touching him, dry circle forming around him on wet pavement, he raises one hand slowly watching lightning dance on fingers. Static locked shot 3 seconds. Sound: continuous electric hum, rain evaporating sizzle, wind stopping around him.<br><br>**Panel 6:** Accidental sneeze triggers massive shockwave explosion outward, bicycle launches into air, trash cans fly backward, streetlights explode in sparks, car alarms trigger everywhere, ZANE horrified hands over mouth. Wide shot shockwave radiating outward. Sound: massive boom, car alarms, shattering glass, objects crashing, ZANE yelping in surprise.<br><br>**Panel 7:** ZANE sprints at full speed, electric trail burning behind him, runs up building wall three steps then falls back confused, cartoon shocked expression mid-air. Dynamic tracking shot maximum speed. Sound: electric whoosh, rapid footsteps, wall impact, ZANE surprised yell.<br><br>**Panel 8:** ZANE floating above city, electricity forming energy wings, legs cycling in panic, looks down at tiny city far below, panic and excitement simultaneously on face. Low angle looking up at floating ZANE. Sound: electric energy hum, wind at height, ZANE panicked laughing.<br><br>**Panel 9:** ZANE dives at full speed catches balloon, lands in hero three-point stance, shockwave from landing, looks up at little girl with biggest gap-tooth smile, hands her balloon, electricity still softly crackling. Medium wide shot warm golden light. Sound: whoosh of dive, heroic landing impact, little girl giggling, soft electric hum.<br><br>**Panel 10:** ZANE stands on rooftop at sunrise, city glowing below, electricity calm and controlled at fingertips, wind catching torn hoodie, gap-tooth smile at horizon, most epic moment. Slow camera pull back from close-up to wide reveal. 5 second hold. Sound: gentle electric hum, wind, birds waking up, distant city waking, triumphant subtle music swell.<br><br>Elements On — include full ambient soundscape for every panel. Subject stays in frame, consistent character, no face morphing, Pixar 3D animation style, exaggerated cartoon physics, smooth motion, no jump cuts, bold saturated colors, electric blue VFX throughout, 24fps, cinematic color grade, 4K resolution. Style reference: The Incredibles, Spider-Man Into the Spider-Verse, Big Hero 6. | [@Viniai_ on X](https://x.com/Viniai_/status/2094674143988105403) |

### Stories & Dialogue

### Product & Ads

#### A Grapefruit Ad That Turns a Desert into a Juice Ocean

A thirsty fennec fox bites into a grapefruit and floods the desert with juice. What starts as a survival scene ends as a summer vacation.

<!-- Replace the placeholder links with your actual URLs. -->

| Final Video | References | Prompt | Source |
| --- | --- | --- | --- |
| [Watch video](https://example.com/grapefruit-ad-result.mp4) | [Reference image](https://example.com/grapefruit-ad-reference.jpg) | **Visual style:** A polished 3D animated commercial with bright, clear colors. Make the fruit pulp and juice look refreshing and give the juice bursts a strong sense of impact. Mix high-end commercial animation with playful absurdity. The fennec fox is cute, expressive, and lively. Use @Image1 as the reference for the character and visual treatment: soft natural light, detailed fur and skin textures, and a miniature-world feel that blends realism with whimsy.<br><br>**0–3s:** A desert under a blazing sun. Heat distorts the air, sand dunes ripple into the distance, and the horizon seems to smoke. A fennec fox lies flat on the scorching sand, its tongue trembling and eyes unfocused. It looks almost dried out. Its long ears droop as though the whole fox is about to evaporate. Sound: labored breathing and faint, exaggerated dry cracking.<br><br>**3–6s:** The fox freezes and twitches its nose. It looks down and discovers an ice-cold grapefruit half-buried in the sand, its peel covered with water droplets. The fruit gleams in the sunlight, with detailed skin texture, like a miracle in the desert. The fox's eyes widen as if it has found its last hope. Sound: a bright discovery ding.<br><br>**6–8s:** The fox lunges toward the grapefruit and hugs it with both paws, pressing its whole face against the peel. Its expression says, “I'm saved.” Freeze the image for one second to create an exaggerated, funny advertising beat. Sound: a soft thump, followed by half a second of silence.<br><br>**8–11s:** The fox bites into the grapefruit. The peel splits, revealing plump, translucent pulp gleaming inside. Instead of trickling out, the juice erupts like a fountain. Sound: a crisp crunch followed by an exaggerated burst of juice.<br><br>**11–16s:** Clear, luminous pink grapefruit juice gushes down the dunes and floods the desert. Dry yellow sand becomes a cool, sparkling pink ocean that feels fresh and fruity. Cacti, rocks, and small dunes disappear beneath the juice. Keep the scene exaggerated and dreamlike. The fox is excited at first, then realizes something is wrong. Its delight turns to shock and fear.<br><br>**16–20s:** Almost submerged in the grapefruit ocean, the fox grabs half a grapefruit like a life ring and floats on the surface. Soaked, it pokes its head out with a bewildered expression. Sunlight glitters across the pink waves. Sound: frantic splashing and waves, with a comic tone.<br><br>**20–23s:** Cut to a white screen. Center the brand name and slogan: “Seedance Grapefruit. Bite into the fruit. Let summer pour out.” A narrator reads the complete line aloud. Sound: a clean, refreshing brand chime.<br><br>**23–29s:** Cut back from the white screen. The fox now lounges on the floating grapefruit, wearing small sunglasses and holding a drink with a straw. It drifts across the juice ocean as though on vacation. Pink fruit pulp, small ice cubes, and splashes float nearby beneath a clear blue sky. The mood shifts from survival to relaxation. The fox stretches out on the grapefruit with a satisfied look. Pull the camera back and freeze on a bright, refreshing, playful summer scene. Sound: relaxed summer music and gently lapping waves.<br><br>**Text:** Apart from the slogan on the white end card, keep on-screen text limited to the brand name. Do not add extra captions. | Volcengine |

### Music & Dance

#### WANDER: A Desert Adventure Music Video

A traveler drives, camps, and hikes through the desert, with electronic music carrying the journey from golden hour to sunrise.

<!-- Replace the final video placeholder with your actual URL. -->

| Final Video | References | Prompt | Source |
| --- | --- | --- | --- |
| [Watch video](https://example.com/wander-music-video.mp4) | None. Text-to-video. | Create a photorealistic cinematic adventure music video following a young traveler through the desert at night and sunrise. Maintain the same face, hair, skin tone, and proportions throughout. Keep the character visually consistent in every shot.<br><br>**Opening:** At golden hour, the traveler drives an old vintage 4x4 across a vast desert highway, wearing a black oversized jacket, white T-shirt, and dark jeans. Show close-ups of hands on the steering wheel, sunlight passing across the windshield, dust rising behind the vehicle, and wide cinematic shots of endless sand dunes.<br><br>**Night campsite:** Hard cut to night. The traveler sets up a small campsite beneath a vast star-filled sky. Show a glowing campfire, boots walking across the sand, sparks floating upward, and the traveler sitting beside the fire while looking toward the stars.<br><br>**Canyon:** Cut to a desert canyon at first light. The traveler hikes through towering red-rock formations, climbs over rocky terrain, and pauses at a high viewpoint overlooking the landscape.<br><br>**Sand dunes:** Hard cut to the traveler running down a steep dune, laughing naturally, spinning in the wind, and watching a distant 4x4 drive across the horizon. Capture realistic wind movement in the clothing and hair.<br><br>**Sunrise road:** Cut to a remote desert road during sunrise. The traveler stands beside the vehicle as the first sunlight illuminates the mountains. Include quick atmospheric shots of tire tracks, desert plants, dust particles, distant birds, rock formations, and sunlight moving across the landscape.<br><br>**Final sequence:** The traveler drives toward the sunrise on an empty road. The camera slowly pulls back into an expansive aerial-style landscape shot as the vehicle becomes tiny against the desert. End with a bold cinematic white title reading “WANDER” over the final sunrise shot.<br><br>**Style:** Premium cinematic adventure music video, photorealistic live-action, 35mm/50mm cinematic lens look, subtle film grain, natural skin texture, realistic hair and fabric movement, handheld camera mixed with smooth tracking shots, dramatic golden-hour lighting, deep blue night tones, realistic firelight, atmospheric dust, natural motion blur, realistic depth of field, 24fps, hard cuts only.<br><br>**Audio:** Energetic cinematic electronic music with atmospheric percussion, deep bass, and subtle acoustic textures. Mix naturally with engine sounds, desert wind, footsteps, fire crackling, and environmental ambience. No dialogue.<br><br>**Avoid:** CGI appearance, plastic skin, identity drift, face changes, distorted anatomy, extra limbs, warped vehicles, impossible landscapes, artificial-looking fire, subtitles, logos, or watermarks. No text other than the final “WANDER” title. | [@ZaraIrahh on X](https://x.com/ZaraIrahh/status/2095736444245479557) |


### Nature & Travel

#### A 1990s NYC Christmas Parade

A nostalgic New York Christmas parade told through quick cuts of balloons, marching bands, and bundled-up spectators, with a 35mm film look and VHS texture.

| Final Video | References | Prompt | Source |
| --- | --- | --- | --- |
| [Watch video](https://x.com/SeeGen_Official/status/2084945937869516834) | None. Text-to-video. | A fast-paced, 20-second montage of a 1990s New York City Christmas parade. Shot on 35mm film with vintage VHS grain and warm, nostalgic Kodak-style lighting. Cut to a new shot every second.<br><br>**0–1s:** Extreme close-up of the bell of a vintage gold trumpet as it plays. Streamers fly past the lens.<br><br>**1–2s:** Low-angle wide shot of a giant retro Captain Underpants balloon drifting between red-brick buildings.<br><br>**2–3s:** Medium shot of a girl in a red 1990s puffer jacket clapping with excitement.<br><br>**3–4s:** Low-angle tracking shot of a Christmas marching band in red uniforms stepping past.<br><br>**4–5s:** Close-up of a child sitting on their father's shoulders, pointing at the sky in wonder.<br><br>**5–6s:** First-person view looking down over a snow-covered street packed with cheering crowds.<br><br>**6–7s:** Quick zoom toward a giant gingerbread-man balloon passing overhead.<br><br>**7–8s:** Close-up of a freshly ejected Polaroid photo as a parade scene gradually develops on it.<br><br>**8–9s:** Medium close-up of three young friends in vintage 1990s outfits, laughing and waving at the parade.<br><br>**9–10s:** High-angle shot of streamers falling like snow onto the parade floats below.<br><br>**10–11s:** Close-up of an old handheld camcorder recording the parade, with a 1990s-style display frame.<br><br>**11–12s:** A quick whip pan reveals a Christmas elf performer on stilts tossing candy to the crowd.<br><br>**12–13s:** Low-angle shot of a giant reindeer balloon towering against the overcast sky.<br><br>**13–14s:** Close-up of colorful Christmas lights blinking around a snow-covered streetlamp. Snowflakes land on the lights and melt.<br><br>**14–15s:** Close-up of wool-gloved hands dropping marshmallows into a steaming cup of hot cocoa.<br><br>**15–16s:** Over-the-shoulder shot of a couple holding hands as an ornate Christmas float passes.<br><br>**16–17s:** Moving tracking shot of a vintage toy-train float rolling down the center of the street.<br><br>**17–18s:** Close-up of a little girl hugging a vintage teddy bear, with light from the falling streamers reflected in her eyes.<br><br>**18–19s:** Low-angle medium shot of a giant snowman balloon gently “waving” to cheering spectators on both sides of the street.<br><br>**19–20s:** Wide finale shot of Santa waving from his sleigh float as colorful streamers and snow fill the air.<br><br>Maintain the 1990s film aesthetic throughout, with energetic quick cuts and fluid transitions between shots. | [@SeeGen_Official on X](https://x.com/SeeGen_Official/status/2084945937869516834) |

### VFX & Transformations

#### Aging from 20 to 80

A woman ages from 20 to 80 in one continuous shot while the reference video's framing, lighting, and performance timing stay the same.

<!-- Replace the placeholder links with your actual URLs. -->

| Final Video | References | Prompt | Source |
| --- | --- | --- | --- |
| [Watch video](https://example.com/aging-result.mp4) | [Reference video](https://example.com/aging-reference.mp4) | Preserve the composition, camera position, lighting, and performance timing of @Video1. Change only the woman's appearance and expression.<br><br>Let her age naturally from 20 to 80. Fine lines around her eyes slowly deepen, a tear slides past the corner of her eye, and the corners of her mouth lift slightly before settling into a faint smile.<br><br>Keep the entire sequence in one continuous shot, with no cuts or flashes. Maintain the alignment of her facial features throughout, without drifting or distortion. | Volcengine |


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

