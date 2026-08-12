---
name: seedance-25
description: "船长AI视界出品的 Seedance 2.5 视频创作技能。Create, improve, extend, edit, or troubleshoot Seedance 2.5 videos and paste-ready prompts, especially on 即梦/Dreamina. Use for text/image/video/audio/reference-to-video, first/last frame, 4–30s clips, 30–180s ultra-long video, native video extension, timestamp control, smart/advanced/video editing, BGM removal, green-screen compositing, creative transfer, viewpoint change, voice reference, multi-person consistency, white-model rendering, seamless transitions, multi-panel storyboards, or Seedance 2.0-to-2.5 prompt migration. Also use when a beginner describes a video idea without knowing modes or prompt terminology. Do not use for non-Seedance models or image-only generation."
---

# 船长AI视界 · Seedance 2.5 OS

> 出品与维护：船长AI视界

Turn an ordinary-language idea into a usable Seedance 2.5 workflow and a prompt the user can paste directly. Do the translation work for the user; teach only when asked.

## Beginner fast lane

Use this path for most requests.

1. Read the idea and infer the simplest viable mode.
2. If the idea is already clear, do not interview the user. Draft immediately.
3. If one missing choice would materially change the result, ask at most two plain-language questions and include a default.
4. Otherwise use these defaults:
   - Surface: 即梦 Web / Seedance 2.5.
   - Duration: 10 seconds for one simple beat; 30 seconds when the idea contains a short beginning, turn, and ending.
   - Frame: 9:16 for short-form/social intent; otherwise 16:9.
   - Resolution: 720p.
   - Sound: natural ambience and motivated effects; no subtitle and no BGM unless requested.
   - Direction: one clear intention; make camera, light, performance, and sound serve it.
5. Return settings, any reference-role map, and one paste-ready prompt. Do not make the user assemble fragments.

## Route the request

| User need | Load |
|---|---|
| Single clip, image-to-video, first/last frame, character prompt | [references/prompting.md](references/prompting.md) |
| Exact limits, formats, durations, resolution, language support | [references/capabilities.md](references/capabilities.md) |
| 30-second story, 30–180s ultra-long video, native extension, timestamp script | [references/long-video.md](references/long-video.md) |
| Smart/advanced/video edit, BGM removal, green screen, viewpoint, creative transfer, seamless transition | [references/editing.md](references/editing.md) |
| Several images/videos/audio clips, audio-only input, identity or role conflicts | [references/references.md](references/references.md) |
| White model, Maya/Blender preview, multi-panel storyboard | [references/white-model-storyboard.md](references/white-model-storyboard.md) |
| A generated take failed or drifted | [references/troubleshooting.md](references/troubleshooting.md) |
| The user wants a ready-made pattern | [references/prompt-recipes.md](references/prompt-recipes.md) |

Load [references/safety.md](references/safety.md) whenever a real person, voice, copyrighted character, brand, graphic harm, sexual content, or evasion-like wording appears.

## Choose the 2.5 workflow before writing

Use the smallest workflow that matches the actual job:

- **Basic generation:** text, first frame, first/last frame, or multimodal references for a new 4–30s clip.
- **Ultra-long video:** one coherent 30–180s story generated as a long-form piece.
- **Native extension:** continue accepted footage forward or backward; preserve the existing portion.
- **Smart edit:** modify an uploaded video with text instructions.
- **Advanced edit:** use annotations such as a box, arrow, line, label, or point on a locally uploaded video.
- **Video edit:** revise an already generated video while preserving the source.
- **White-model render:** transfer camera, blocking, motion, space, or render treatment from a 3D preview.

Do not force a long story into repeated short generations when ultra-long mode is available and continuity matters. Do not regenerate a correct video when only one layer needs editing.

## Replace obsolete 2.0 assumptions

Treat these as 2.5 resets:

- Do not assume one visible beat is the universal maximum. A 30s or ultra-long prompt may contain several ordered beats when each has a timestamp and readable transition.
- Do not default to chained clips for length. Prefer ultra-long mode for a complete 30–180s story; prefer native extension for continuing an accepted clip.
- Do not reuse 2.0 reference ceilings. Load the 2.5 capability sheet before quoting numbers.
- Do not assume audio-only reference is unsupported.
- Do not treat negative instructions such as “no subtitle” or “no BGM” as inherently ineffective. State them clearly, and repeat them once as a global constraint when important.
- Do not limit video reference to raw motion transfer. 2.5 can use a reference for creative rhythm, emotion, camera language, or concept, but still assign one authority per dimension.
- Do not solve a local defect by rewriting the whole prompt. Use edit mode, annotations, and a time range.
- Do not treat green screen, white model, viewpoint modification, seamless transition, or multi-panel storyboards as hacks; route them as first-class workflows.

## Build every prompt in four layers

Use only the layers the request needs:

1. **Reference declaration:** map each `@图片` / `@视频` / `@音频` to identity, scene, motion, camera, timing, voice, music, or another single primary role. State exclusions when leakage is plausible.
2. **One-line overview:** subject + place + event + genre/look + exceptional camera idea.
3. **Visible progression:** write a story line for a simple clip or timestamped segments for multi-beat work. Each segment may include image content, camera, action, dialogue, sound, and a visible endpoint.
4. **Global lock:** repeat only constraints that must hold throughout—identity, costume, scale, scene continuity, sound policy, subtitle/BGM policy, and failure-prone anatomy or props.

For edit work, replace the four-layer structure with: `annotation/position + exact target + A→B change + active time range + what must remain unchanged`.

## Control complexity

Give every controlled dimension one owner. Identity, motion, camera, scene, timing, audio, and style may come from different references, but no dimension may have two competing owners. Remove references that own nothing.

For multiple beats, write causal order: initial state → trigger → decisive change → response → endpoint. Let the camera cover the important change rather than decorating the prompt with several unrelated moves.

## Fact and observation gate

Load [references/capabilities.md](references/capabilities.md) before stating a limit. Its numbers come from the linked 即梦 Seedance 2.5 guide and describe that documented surface/version. For APIs, routers, pricing, model IDs, regions, or other products, verify current official documentation; never generalize the 即梦 Web limits to every surface.

Never claim to have watched, heard, measured, or verified an attachment or returned take unless the current client actually exposed it. If it cannot be inspected, use the user's description and label it as user-reported.

## Output contract

Unless the user asks for another format, return:

1. **Recommended setup:** mode, duration, frame, resolution, and required uploads.
2. **Reference map:** only when references exist.
3. **Paste-ready prompt:** natural language in the user's language; preserve every reference tag exactly.
4. **One practical note:** only when it prevents a likely failure.

Do not return internal gate names, a long tutorial, or several competing prompts to a beginner. Give one best default first. Add alternatives only when the user asks to explore.
