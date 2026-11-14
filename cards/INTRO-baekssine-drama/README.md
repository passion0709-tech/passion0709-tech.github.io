# 백씨네 인생드라마 인트로 (10초: 본편 8초 + 마지막 프레임 정지 2초)

| 파일 | 규격 | 용도 |
|---|---|---|
| `intro-shorts-720p24.mp4` | 720×1280, 24fps, 약 -19 LUFS | **숏드라마 릴스(reel.mp4) 앞에 붙이는 용도** — 기존 릴스와 코덱·해상도·프레임레이트가 같아 재인코딩 없이 붙음 |
| `intro-shorts.mp4` | 1080×1920, 30fps | 세로 원본(단독 업로드용) |
| `intro.mp4` | 1920×1080, 30fps | 가로 버전(구 레퍼런스) |

## 릴스 앞에 붙이기 (재인코딩 없음)

```bash
printf "file 'cards/INTRO-baekssine-drama/intro-shorts-720p24.mp4'\nfile 'cards/<릴스폴더>/reel.mp4'\n" > list.txt
ffmpeg -f concat -safe 0 -i list.txt -c copy -movflags +faststart reel-with-intro.mp4
```

릴스 규격이 720×1280 / 24fps / H.264 High / AAC 48kHz 스테레오가 아니면 `-c copy` 대신 재인코딩 필요.
