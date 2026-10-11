# 拍照姿勢資料庫

線上使用：https://mshmwr.github.io/pose-reference/

從團體照裡一格一格裁出來的拍照姿勢範本，分男生／女生，也可以依類型（動態、站姿、坐姿、手勢、互動）和來源照片篩選。

- 點任何一張就能全螢幕練習：上一個 / 下一個 / 隨機、鏡像、自動換（5–20 秒）、3 秒倒數
- 「新增範本」：載入照片、框出每個人、設定名稱／性別／類型，馬上出現在資料庫（只存在自己的瀏覽器）
- 要永久收進資料庫：按「複製資料」，把資料連同照片加進 repo

## 資料結構

- `photos/<id>.jpg` — 原始團體照
- `poses.json` — 所有範本

```json
{
  "photos": [{ "id": "sorezore-no-isu", "title": "乃木坂46「それぞれの椅子」", "file": "photos/sorezore-no-isu.jpg", "w": 600, "h": 532 }],
  "poses": [{ "id": "sorezore-no-isu-01", "photo": "sorezore-no-isu", "box": [175, 265, 300, 483], "name": "…", "gender": "female", "tags": ["動態"] }]
}
```

`box` 是 `[x0, y0, x1, y1]`，單位是原始照片的像素；`gender` 是 `female` 或 `male`。

單一 `index.html`，不需要 build。
