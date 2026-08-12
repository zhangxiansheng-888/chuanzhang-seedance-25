# White-model and storyboard workflows

> 船长AI视界整理与维护

## Choose white-model granularity

| Type | Use it for | Prompt architecture |
|---|---|---|
| Coarse white model | Camera, movement path, blocking, position, light change, edit rhythm | reference declaration + model-to-character mapping + story/action + scene treatment + global locks |
| Fine white model | Material, lighting, style, and production rendering of an already detailed model | render command + timestamped render description + scene treatment + global locks |

## Coarse white model

Treat simple spheres, cylinders, boxes, or low-detail figures as a dynamic skeleton, not as final appearance.

Template:

```text
参考@视频1的运镜、动作路径、角色站位与镜头节奏。
将其中[shape/color model]映射为@图片1的[character]；将[other model]映射为@图片2的[prop/character]。
[Describe the ordered action, expressions, dialogue, and light change.]
场景使用@图片3的[environment]。
全程保持角色身份、比例、站位逻辑和动作连续；不保留白模材质、轨迹线、坐标线或相机锥体。
```

If a coarse model has limbs or wings, write the complete action sequence. Simple geometry without detailed limbs often transfers more reliably than a poorly articulated rig.

## Fine white model

Start with `将@视频1的白模动画渲染成最终成片`. Divide material, lighting, environment, and transitions by time. Keep object geometry, scale, camera, and spatial logic fixed unless the user requests a change.

Remove trajectory lines, coordinate axes, camera cones, viewport overlays, and other guide artifacts from the reference before upload when possible.

## Maya/Blender workflow

Use the 3D preview to establish camera route, staging, position, and movement. Export a clean viewport/reference video, upload it to 即梦, then map every model to its final character or object and describe the final materials, lighting, environment, and sound.

## Multi-panel storyboard

Recommended prompt order:

1. Declare that the uploaded grid is an ordered storyboard and explain whether each panel is a complete shot.
2. Map characters, locations, and props to separate identity references.
3. Walk through panels in order; fill the gaps with composition, shot size, camera, action, and transition.
4. Add global look, continuity locks, sound policy, and prohibited elements.

Template:

```text
@图片1是按左到右、上到下排列的[N]格连续分镜，每格代表一个完整镜头。
角色A参考@图片2，角色B参考@图片3，场景参考@图片4。
镜头1（0–Xs）：[composition, shot size, camera, action, endpoint].
镜头2（X–Ys）：[bridge from previous endpoint, camera, action, endpoint].
...
全片保持人物、服装、比例、道具、光线方向与空间连续；镜头衔接自然；无字幕、无Logo、无无关人物。
```

Simple line art or stick-figure storyboards are acceptable because the prompt and identity references supply the finished design.
