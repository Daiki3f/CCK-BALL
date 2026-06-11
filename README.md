zmk-config for CCK_BALL (4x6)
![白色成品+手托](https://github.com/user-attachments/assets/7b2834f0-ca09-4f8c-9fc1-12455f67ae44)
![白色成品2](https://github.com/user-attachments/assets/7fe073d5-bb1c-4e42-b150-3521b4418ae0)
![黑色成品1](https://github.com/user-attachments/assets/4a7023ca-07ca-4a63-9d32-9af96ff9c73f)
![黑色成品2](https://github.com/user-attachments/assets/34d4351d-cbd9-4c82-a2e0-c7c9d28c5942)

# CCK-BALL 開発メモ

## 現在の開発環境

- キーボード: WK CCK BALL
- MCU: nice!nano v2
- ファームウェア: ZMK
- 管理方法: GitHub + GitHub Actions
- PC: Windows

---

# 日常の開発手順

## 1. keymap編集

編集対象

```text
config/cck_ball.keymap
```

変更後

```powershell
git add .
git commit -m "変更内容"
git push
```

---

## 2. GitHub Actionsでビルド

GitHub

Actions

↓

CCK-BALL

↓

Build

↓

完了を待つ

---

## 3. UF2ダウンロード

Actions

↓

最新Run

↓

Artifacts

↓

ダウンロード

生成されるファイル

```text
cck_ball_left-nice_nano_v2-zmk.uf2
cck_ball_right-nice_nano_v2-zmk.uf2
settings_reset-nice_nano_v2-zmk.uf2
```

---

## 4. キーボードへ書き込み

### 右側

物理RESETボタン2回

↓

NICENANO表示

↓

cck_ball_right-nice_nano_v2-zmk.uf2 をコピー

↓

NICENANOが消える

↓

再起動

---

### 左側

物理RESETボタン2回

↓

NICENANO表示

↓

cck_ball_left-nice_nano_v2-zmk.uf2 をコピー

↓

NICENANOが消える

↓

再起動

---

# よくある誤解

## Windowsエラーが出ても書き込み成功の場合がある

エラー例

```text
0x800701B1
0x80070037
```

nice!nanoは書き込み後すぐ再起動する。

そのためWindowsが

「ドライブが消えた」

と判断してエラーを出すことがある。

まず実際の動作を確認すること。

---

# Bluetooth復旧手順

## 症状

- Bluetooth接続できない
- Studioが見つからない
- 左右通信しない

---

## 対処

BTレイヤーへ移動

↓

BT_CLR_ALL

実行

↓

WindowsのBluetooth設定から

WK CCK BALL

を削除

↓

再ペアリング

---

# 完全リセット

## settings_reset

使用ファイル

```text
settings_reset-nice_nano_v2-zmk.uf2
```

実行すると

- Bluetooth情報削除
- Studio設定削除
- 保存設定削除
- 左右ペア情報削除

される

---

## 復旧方法

1. settings_resetを書き込む
2. leftファームを書き込む
3. rightファームを書き込む
4. Bluetooth再設定
5. Studio接続確認

---

# Bootloader確認

物理RESETボタン2回

↓

NICENANOドライブが表示される

確認ファイル

```text
INFO_UF2.TXT
```

正常例

```text
Model: nice!nano
Board-ID: nRF52840-nicenano
```

---

# 緊急復旧チェックリスト

## 動かない時

□ ActionsはSuccessか

□ left/rightを間違えていないか

□ NICENANOに入れるか

□ INFO_UF2.TXTが見えるか

□ BT_CLR_ALLしたか

□ Windows側Bluetooth登録を削除したか

□ 最新Artifactsを書き込んだか

---

# 今後の方針

GitHubを正本にする。

変更は

```text
cck_ball.keymap
```

で管理。

Studioは動作確認用。

最終的な設定はGitHubへ反映する。