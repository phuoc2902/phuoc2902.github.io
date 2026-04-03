---
title: "Unity 2D Survivor Wave – dự án game top-down của mình"
draft: false
tags: ["Unity", "C#", "GameDev", "Project"]
author: ["Trương Huy Phước"]
summary: "Dự án game Unity 2D (top-down/survivor wave): vòng lặp wave → shop → wave, 2 chế độ vũ khí, hệ EXP/level-up và scaling độ khó."
cover:
  image: "/images/demoanhgame.png"
  alt: "Unity 2D Survivor Wave"
  caption: "Unity 2022.3.24f1 · Top-down · Survivor wave"
  relative: false
---

### Giới thiệu dự án

Đây là dự án **game Unity 2D** theo phong cách **top-down / survivor wave** mà mình làm trong giai đoạn còn khá sớm. Trọng tâm của project là vòng lặp gameplay “đánh theo wave”, có nghỉ giữa các wave để mua/nâng cấp, kết hợp hệ EXP/level-up và 2 kiểu chiến đấu (đánh xa/đánh gần).

### Thông tin project

- Đây là dự án game Unity 2D (top-down/survivor wave) chạy trên Unity 2022.3.24f1: `ProjectSettings/ProjectVersion.txt`
- Package đáng chú ý: Cinemachine, TextMeshPro, 2D Feature, Visual Scripting, Unity Test Framework: `Packages/manifest.json`
- Scene chạy chính (và hiện là scene duy nhất trong Build Settings): `Assets/Scenes/SampleScene.unity`: `ProjectSettings/EditorBuildSettings.asset`

### Luồng gameplay (nhìn từ code + scene)

- Vào game: `GameManager.Start()` gọi `StartGame()`, bắt đầu đếm thời gian và cập nhật UI, phím H bật/tắt màn hướng dẫn và pause bằng `Time.timeScale`: `GameManager.cs`
- Player: di chuyển 2D, có máu/level/exp/coin, lên level sẽ pause game và mở panel nâng cấp: `Player.cs`
- Wave/quái: `MonsterSpawner` sinh quái theo từng wave, sinh theo “burst” quanh player, wave xong mở shop và pause game: `MonsterSpawner.cs`
- Đổi vũ khí: nhấn R chuyển ranged ↔ melee có thời lượng và cooldown, có UI `fillAmount`: `WeaponSwitcher.cs`
- Khi player chết: `Player.Die()` gọi `MonsterSpawner.PlayerDiedAndReset()` để reset điểm, reset wave, xoá quái và reset chỉ số: `Player.cs`, `MonsterSpawner.cs`

### Kiến trúc script (các “khối” chính)

- Core/UI
  - `GameManager`: time/score UI, help menu, restart: `GameManager.cs`
  - `Player`: exp/level, upgrade panel, máu, coin lưu bằng `PlayerPrefs`: `Player.cs`
- Wave/Spawner
  - `MonsterSpawner`: quản lý wave, spawn/despawn, shop, tăng/giảm độ khó theo “loop” và số lần chết: `MonsterSpawner.cs`
  - Data wave dùng class/struct serializable (được cấu hình trực tiếp trong Inspector): `WaveData.cs`, `MonsterWaveData.cs`
- Enemy
  - Base abstract class `Monster`: chase player, máu, slider HP, drop item theo xác suất, báo về spawner khi chết: `MonsterLopCha.cs`
  - Các biến thể: Orc (đánh gần), OrcBerserker (berserk), Orc_Shaman (heal/né player), Boss (thực chất là “goblin boss”): `Enemy_Orc.cs`, `OrcBerserker.cs`, `Orc_Shaman.cs`, `BossScript.cs`
- Combat/Item
  - Ranged gun bắn prefab đạn + cộng `bulletDamageBonus`: `VuKhi.cs`, đạn: `PlayerBullet.cs`
  - Melee dùng stamina + `OnCollisionStay2D` gây damage theo tick + hút máu: `VukhiCanChien.cs`
  - Exp pickup + “nam châm” hút exp: `ExpEnemy.cs`, `ExperienceMagnet.cs`
  - Coin pickup đang bị làm 2 nơi (trong `Player.OnTriggerEnter2D` và trong `Coin.OnCollisionEnter2D`): `Player.cs`, `Coin.cs`

### Cấu hình trong scene

- `GameManager` và `Player` được đặt trực tiếp trong scene, `Player` đã gán reference sang `MonsterSpawner`: `SampleScene.unity`
- `MonsterSpawner` nằm trên GameObject tên “WaveSpawnerManager”, wave được cấu hình inline trong scene (Wave 1/2/3/Boss), shop button gọi `BuyHealth()`: `SampleScene.unity`

### Nhận xét nhanh (điểm mạnh / rủi ro)

- Điểm mạnh: gameplay loop khá rõ (wave → shop → wave), có scaling độ khó theo vòng lặp, có hệ vũ khí 2 mode, có hệ exp/level-up.
- Rủi ro kỹ thuật:
  - Trùng trách nhiệm điểm số: `GameManager.cs`, `MonsterSpawner.cs`
  - Nhiều chỗ dùng `FindObjectOfType`, `GameObject.Find`, phụ thuộc tag/name (“Player”, “GameManager”, “AmmoText”, “Stamina”)
  - Folder/script naming không đồng nhất (Scipt, Scripe, class/file lệch tên)
  - Repo chứa cả `Library/` và `Logs/`, không thấy `.gitignore`

### Tình trạng demo & source code

Vì đây là **một trong những dự án đầu tay của mình vào năm 2 đại học**, nên đến hiện tại **demo và source code đầy đủ đã bị mất** (mình chỉ còn lại phần mô tả/ghi chú về cấu trúc và luồng gameplay như bên trên).

### Cách chạy (tham khảo)

- Mở project bằng Unity Hub → Unity 2022.3.24f1
- Mở scene: `SampleScene.unity` và bấm Play
- Input chính: WASD/Arrow (di chuyển), chuột trái (bắn/đánh), chuột phải (reload ranged), R (đổi vũ khí), H (mở hướng dẫn/pause)
