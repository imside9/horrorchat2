# 기억의 늪: 심연 — AI 이미지 생성 프롬프트

## 공통 네거티브 프롬프트
```
bright colors, cheerful, cartoon, anime, text watermark, logo, daylight, happy mood
```

---

## 프로필 이미지 (512x512 정사각형)

### 1. `images/profile_minsu.png` — 민수
```
Dark, eerie portrait of a Korean young man in his late 20s, slightly blurred face, pale skin, wet hair as if soaked in rain, hollow dark eyes staring directly at camera, faint unsettling smile, black background, low-key lighting, horror atmosphere, profile picture style, square crop, muted cold tones, digital noise grain overlay
```

### 2. `images/profile_younghun.png` — 김영훈
```
Portrait of an ordinary Korean man in his late 20s, slightly nervous expression, neat short hair, wearing a casual collared shirt, warm indoor lighting, normal-looking messenger profile photo style, square crop, natural skin tone, slightly desaturated colors, clean background
```

### 3. `images/profile_jisu.png` — 박지수
```
Portrait of a Korean woman in her late 20s, shoulder-length hair, soft features, gentle but slightly worried expression, minimal makeup, wearing a simple top, soft indoor lighting, messenger profile photo style, square crop, natural tones, clean light background
```

### 4. `images/profile_me.png` — 나 (주인공)
```
Back of a Korean man's head silhouette, dark moody lighting, standing in front of a window with rain streaks, anonymous mysterious feel, no face visible, dark green and black tones, profile picture style, square crop, cinematic mood
```

### 5. `images/profile_unknown.png` — 알 수 없는 사용자
```
Completely distorted glitch art profile picture, corrupted digital image of a human silhouette, heavy VHS static noise, RGB color split effect, scan lines, no recognizable face, dark background with digital artifacts, cyberpunk horror aesthetic, square crop, unsettling and abstract
```

---

## 스토리 이미지 (1024x576, 16:9)

### 6. `images/lake_rain.jpg` — 프롤로그: 비 오는 호수
```
A dark, misty lake at night during heavy rain, Korean countryside fishing reservoir, dense fog rolling over black water surface, distant silhouette of a small wooden bungalow with a single dim light, rain drops hitting water creating ripples, ominous and lonely atmosphere, cold blue-grey color palette, cinematic wide shot, horror film still, no people visible, extremely moody and unsettling
```

### 7. `images/newspaper.jpg` — Act 2: 실종 사건 신문기사
```
Close-up photo of a Korean newspaper article clipping, yellowed aged paper texture, headline in Korean bold text reading "낚시터 실종 사건" (fishing reservoir missing person case), blurry body text below, a small grainy black-and-white photo of a lake embedded in the article, coffee stain on corner, slightly crumpled paper, realistic newspaper photography style, overhead shot on dark wooden table, dramatic side lighting
```

### 8. `images/cctv.jpg` — Act 3: 첫 번째 CCTV (민수의 주장 — 왜곡)
```
Grainy low-quality CCTV security camera footage, nighttime, heavy rain, a dark wooden dock at a lake, two human silhouettes — one figure appears to be shoving or pushing the other toward the black water, the victim stumbling forward off the edge, angle makes it look like a deliberate push, green-tinted night vision look, timestamp overlay "2023.08.14 02:47:12" in corner, heavy VHS static and scan lines, blurry and low resolution, wide angle surveillance camera perspective, deeply incriminating and disturbing
```

### 9. `images/cctv2.jpg` — Act 3: 두 번째 CCTV (다른 각도 — 혼란)
```
Grainy low-quality CCTV security camera footage from a DIFFERENT elevated angle, nighttime, rain visible in frame, a wooden dock at a dark lake, two people struggling near the water's edge, and a THIRD dark shadowy figure standing several meters behind them — barely visible but clearly a person watching, ambiguous chaotic action near the water, impossible to tell who is pushing whom, green-tinted night vision look, timestamp overlay "2023.08.14 02:47:33" in corner, scan lines, VHS distortion, wide angle surveillance camera perspective, extremely unsettling and confusing, the third figure is the most disturbing element
```

### 10. `images/cctv_full.jpg` — Act 4: 전체 CCTV (진실)
```
Grainy CCTV security camera footage at night, a wooden dock at a dark lake, one person is clearly JUMPING forward into the black water on their own — arms forward, body lunging, unmistakably voluntary and deliberate, a second person behind is desperately REACHING OUT with both arms trying to grab the jumper's clothes but failing — fingers just missing, the gap between them showing the failed rescue attempt, rain pouring heavily, green-tinted night vision, timestamp "2023.08.14 02:47:51" overlay, VHS static and scan lines, wide surveillance angle, tragic moment — the jumper is clearly acting on their own will while the other person tries and fails to save them
```

### 11. `images/group_photo.jpg` — Act 4: 모자이크 단체사진
```
A casual group photo of four young Korean friends (3 men and 1 woman) in their mid-20s, taken outdoors at a fishing spot or lakeside, daytime, summer clothing, everyone smiling, but ONE person's face on the far right is heavily pixelated/mosaic censored creating an unsettling contrast, the other three faces are clear, slightly faded vintage photo filter, warm but nostalgic tones, polaroid-style or phone camera quality
```

---

## CCTV 타임스탬프 연출

| 영상 | 시간 | 의미 |
|------|------|------|
| cctv.jpg | 02:47:12 | 편집된 앞부분 — 미는 것처럼 보이도록 자른 것 |
| cctv2.jpg | 02:47:33 | 다른 각도 — 제3자 존재 암시 |
| cctv_full.jpg | 02:47:51 | 결정적 순간 — 자발적 점프와 실패한 구조 |
