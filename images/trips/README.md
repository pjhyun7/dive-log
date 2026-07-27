# 트립 사진

트립별 폴더에 사진을 보관합니다. 각 폴더의 **`cover.*`** 1장이 PHOTO LOG에 노출되고, 나머지 사진은 아카이브로 저장만 됩니다(현재 사이트에는 cover만 표시).

## 폴더 구조

```
images/trips/
├─ yangyang/     (양양)
│  ├─ cover.webp        ← PHOTO LOG에 뜨는 대표 1장
│  └─ (원본·추가 사진 자유롭게)
├─ bunaken/      (부나켄)
├─ similan/      (시밀란 리브어보드)
├─ phuket/       (푸켓)
├─ bohol/        (보홀)
├─ miyakojima/   (미야코지마)
├─ dahab-aowd/   (다합 AOWD)
└─ dahab-owd/    (다합 OWD)
```

`.gitkeep` 은 빈 폴더를 git에 올리기 위한 빈 파일입니다. 사진을 넣으면 지워도 됩니다.

## 연결 방법

`index.html` 의 `const TRIP_STORIES` 에서 해당 트립 `cover` 를 폴더 안 파일 경로로 바꿉니다.

```js
'Bunaken': {
  summary: '...',
  cover: 'images/trips/bunaken/cover.webp',   // ← null 에서 변경
  species: []
}
```

트립 키 → 폴더 매핑: `Dahab OWD`→dahab-owd · `Dahab AOWD`→dahab-aowd · `Miyakojima`→miyakojima · `Bohol`→bohol · `Phuket`→phuket · `Similan Liveaboard`→similan · `Bunaken`→bunaken · `양양`→yangyang

## 이미지 규칙

- 대표 사진 파일명: **`cover.webp`** 권장 (JPG·PNG·GIF·애니메이션 WebP 도 `<img>` 로 동작)
- 비율: **가로형** 3:2 또는 16:9 (카드가 가로로 크롭됨)
- 크기: 긴 변 960~1280px, 100~250KB
- PHOTO LOG 는 **사진이 등록된 모든 트립**을 최신순으로 표시. cover 가 `null` 이면 표시 안 함.
