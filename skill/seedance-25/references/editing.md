# Editing and 2.5 transformation workflows

> 船长AI视界整理与维护

## Choose the edit surface

- **智能编辑:** select the mode in video generation, upload a video, and describe the modification in text.
- **高级编辑:** for a local upload, add a box, arrow, line, text label, or point to target an area precisely.
- **视频编辑:** revise an already generated video from its result controls.

Preserve the source video and change only the requested layer.

## Edit formula

Use:

`[annotation/position] + [exact target] + [A→B change] + [active time range] + [preserve list]`

Example structure:

`在0–8秒，将红框内男生的蓝色牛仔裤替换为深黑色西装裤，全片颜色和材质保持一致；保留人物身份、动作、机位、背景、光影与原始节奏不变。`

Say whether the change exists throughout, appears gradually, or only occurs within a time range.

## BGM separation or removal

Name what to remove and what to preserve:

`移除整段视频的背景音乐，仅保留人物原声、对白、环境声和画面中的原有字幕；画面、剪辑节奏与口型不变。`

If the desired output is silent, state `去掉全部声音，保持静音` instead.

## Local removal or replacement

Identify the object, its location, active time, replacement behavior, and background reconstruction:

`从3–7秒无痕移除地标点处的咖啡杯，补全被遮挡的桌面纹理与阴影；人物手势和其余物体不变。`

## Viewpoint modification

State the new camera position and which spatial facts remain fixed. Ask the model to extrapolate unseen space consistently:

`将机位改为角色左后方45度中景，保持人物动作、时间、服装和桌面物品位置不变，合理补全原镜头未出现的房间空间。`

## Creative transfer

Assign the donor video only the dimensions wanted: choreography, pacing, emotion, camera language, visual concept, or transition idea. Explicitly exclude donor performer, costume, scene, logo, and voice unless authorized.

`@视频1只提供紧张递进的节奏、手持跟拍语言和最后的急停动作；人物身份、服装、场景与品牌不得迁移。@图片1控制新角色身份。`

## Green-screen compositing

Provide the green-screen source and target scene/reference. Lock perspective, contact, edge quality, lighting direction, color spill removal, motion blur, and shadows:

`将@视频1绿幕人物自然合成到@图片1的夜间街道，清除绿色溢色；匹配右侧霓虹主光、地面接触阴影、透视和运动模糊，人物动作与口型不变。`

## Seamless transition between two videos

Preserve both originals and generate only the bridge. Describe a shared physical carrier at the join—shape, color, occlusion, movement direction, particles, gaze, or object.

`不修改@视频1与@视频2。让@视频1尾帧的[carrier]沿[direction]遮满画面，在遮挡中转化为@视频2开头的[matching carrier]；位置、尺寸、速度和运动方向连续，禁止黑屏、跳帧、硬切、闪烁、字幕与Logo。`

## Voice and multi-person work

- State which reference owns each voice and which character speaks each line.
- Give every character distinct face, hair, clothing, position, and role.
- Repeat `不串脸、不互换声音、不互换动作` when several people share the frame.
