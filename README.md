# zmk-config-moNa2-v2

moNa2 v2とCOROPIT向けの個人用ZMK設定です。

日本語入力には[大西配列](https://o24.works/layout/)を使用しています。大西配列はローマ字100万字の統計を基に設計されたキー配列です。母音と子音を左右へ分けることで両手の交互打鍵を増やし、指の移動と同じ指の連続使用を抑えています。

![Keymap](keymap-drawer/mona2.svg)

## 主な機能

- 大西配列をベースにした42キー向けkeymap
- Home Row ModsとSandS
- 左右どちらの手でも使えるMouse layer
- Trackball操作で10秒間Mouse layerを自動有効化
- `H`holdによるTrackball scroll
- `P`holdによるTrackball gesture
- ZMK Studio対応
- USBとBluetooth出力の切り替え
- COROPIT向けTrackball軸反転

## Trackball操作

### Mouse layer

Trackballを動かすとMouse layerが10秒間有効になります。Mouse layerでは左右どちらの手でもmouse buttonを操作できます。

| キー | 動作 |
| --- | --- |
| `I` / `S` | Middle click |
| `O` / `T` | Left click |
| `A` / `N` | Right click |
| `X` / `J` | Button 5 |
| `V` / `D` | Button 4 |

### Scroll

`H`をholdしながらTrackballを動かすとscrollします。`H`をtapした場合は通常の`H`が入力されます。

### Gesture

`P`をholdしながらTrackballを動かすとbrowser tabを操作します。`P`をtapした場合は通常の`P`が入力されます。

| Trackball方向 | 動作 | Shortcut |
| --- | --- | --- |
| 左 | 前のtab | `Ctrl+Shift+Tab` |
| 右 | 次のtab | `Ctrl+Tab` |
| 上 | 新規tab | `GUI+T` |
| 下 | tabを閉じる | `GUI+W` |

## Layer構成

| Layer | 用途 | 起動方法 |
| --- | --- | --- |
| Main | 大西配列 | Default |
| Lower | Function keyと数字 | `Tab`hold |
| Raise | 記号とcursor | `Space`holdまたは`Enter`hold |
| Ctrl | Bluetoothと出力設定 | `GUI+W`hold |
| Mouse | Mouse button | Trackball操作で自動起動 |
| Scroll | Trackball scroll | `H`hold |
| Gesture | Browser tab操作 | `P`hold |

## COROPIT設定

右側TrackballはCOROPIT向けにX軸とY軸を反転しています。

滑らかさを優先してPMW3610を次の設定で動作させています。

- CPI: `3200`
- Sampling interval: `4ms`
- Report interval limit: `0ms`
- Bluetooth connection interval: `7.5ms`

省電力設定より電池消費が増える点に注意してください。

## Build

`main`へのpushでGitHub Actionsが左右のfirmwareとsettings reset firmwareをbuildします。生成されたfirmwareはworkflowのArtifactsから取得できます。

## 参考

- [大西配列](https://o24.works/layout/)
- [moNa2 v2](https://github.com/Arai-yt/zmk-config-moNa2-v2)
- [ZMK Firmware](https://zmk.dev/)
