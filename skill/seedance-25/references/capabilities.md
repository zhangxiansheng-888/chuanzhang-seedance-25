# Seedance 2.5 capability sheet

> 船长AI视界整理与维护

Source: [《【即梦】Seedance 2.5 使用手册》](https://bytedance.larkoffice.com/wiki/RXh5ww6EqighMdkVTMccm2d4n7e), read 2026-08-02, document revision 8502.

Treat these as documented 即梦 Seedance 2.5 facts, not universal promises for every API or router. Verify volatile surface claims before quoting them externally.

## Output and modes

| Item | Documented behavior |
|---|---|
| Basic generation | 4–30 seconds (`duration -1` or 4–30; 97–721 frames) |
| Resolution | 480p and 720p |
| Ultra-long mode | 30–180 seconds in one long-form generation |
| Native extension | Extend a source no longer than 30s by 4–30s; the result can reach 60s |
| Extension chaining | A newly generated result may be extended again while that result is still no longer than 30s |
| Timing control | Text instructions may target exact seconds/timestamps |
| Main 即梦 modes | 全能参考, 智能编辑, 超长视频, 首尾帧; local uploads can expose 高级编辑; generated results can use 视频编辑 |

Extension wording in the guide contains both “30 seconds以内” and an example using a 30-second source. When the UI rejects the boundary value, follow the live UI rather than arguing from the text.

## Reference input limits

| Type | 2.5 documented ceiling | Useful technical constraints |
|---|---:|---|
| Images | Up to 30 | jpeg/png/webp/bmp/tiff/gif/heic/heif; aspect ratio 0.4–2.5; width/height 300–6000px; each under 30MB |
| Videos | Up to 10, combined duration no more than 30s | mp4/mov; 480p–4K; 24–60fps; each about 2–30s; each under 200MB |
| Audio | Up to 10, combined duration no more than 30s | wav/mp3; each about 2–30s; each under 15MB |
| Audio-only reference | Supported | A picture or video is no longer mandatory for reference-to-video |

The guide also notes implementation tolerances around 1.8–30.2s for individual assets, but use the clean user-facing 2–30s rule unless an API integration requires the exact boundary.

## Practical sweet spots from the guide

- Use 1–5 video/audio subjects for better stability; 6–10 may require retries.
- Prefer 5–10s subject video/audio references; longer inputs can become less stable.
- Use 1–8 image subjects for better stability; 9–12 may require retries.
- For more than five subjects, separate different views into multiple images. Several single-view images are more stable than one collage containing many views.
- Keep a video-edit source within 20s when possible.
- Use 1–5 reference images for video-reference editing; 6–8 may work with lower stability.

These are quality recommendations, not hard input rejections.

## 2.5 improvements to design for

- Lower synthetic/“AI face” appearance, stronger physical texture, cut consistency, complex actions, and long-tail motion.
- Better response to requests that remove accidental subtitles or unrelated BGM.
- Better small-language understanding, with highlighted support for Chinese, English, Spanish, Indonesian, Malay, Thai, Arabic, Portuguese, Vietnamese, Japanese, and Korean.
- More precise multimodal editing: BGM separation/removal, creative transfer, local removal/editing, viewpoint change, improved voice reference, improved multi-person identity, green-screen compositing, white-model control, seamless transitions, and multi-panel storyboards.

## Fact discipline

- Keep “model capability,” “feature exposed on this surface,” “request syntax,” and “returned adherence” separate.
- A documented feature is not a guarantee that every generation obeys it.
- Do not quote API model IDs, prices, or third-party limits from this sheet.
