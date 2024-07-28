# slot-contents-updated-sample

## 概要

Vue.jsのコンポーネントについて、slotコンテンツが変更されたときにupdatedがトリガーされない現象の動作確認をするプロジェクト。

## 説明

- src/components/ParentComponent.vue
  - slotコンテンツを挿し込む側のコンポーネント
- src/components/ChildComponent.vue
  - slotコンテンツを挿し込まれる側のコンポーネント
- src/views/HomeView.vue
  - 各箇所で設定しているupdatedフックが実行された際のログを表示する。
