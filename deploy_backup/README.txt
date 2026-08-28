香典返しe-shop ShopServe設定バックアップ
取得日時: 2026-08-28（本番実装前）
取得方法: 管理画面の各編集欄の値を読み取り専用で取得（ShopServe側は未変更）

■ backup_0828_0838.json
- smp_shop_top: スマートフォンサイト設定 > お店ページ（トップ）の全入力値
  （freeareaFreearea_0〜4 のHTML、layoutToppage ほか 39項目）
- smp_header_footer: スマートフォンサイト設定 > ヘッダ・フッタ設定の全入力値
  （commonHeader / commonFooter / regiFooter ほか 138項目。ラジオ・チェックは value:checked/unchecked 形式）

■ backup_pc_0828_0918.json
- ヘッダとSEO: デザイン設定 > ヘッダとSEOの設定の全textarea
  h_key / h_desc / h_expert_headtag(head追記) / h_expert_tag(ヘッダーHTML) /
  h_expert_tag_cart / h_banner / f_banner(フッター上バナー=特典セクション10,932字) /
  f_expert_tag(フッターHTML) ほか
- 全体のレイアウト / HTMLカスタマイズ / CSSカスタマイズ: この時点ではtextarea未検出
  （画面操作が必要なタイプ。特定でき次第、追加バックアップを取得予定）

■ 復元方法
該当画面を開き、JSON内の値を対応する欄へ貼り戻して保存・お店ページを更新する。
フリーエリアの変更 → 「利用中のテーマでお店を更新」
head追記・HTML/CSSカスタマイズの変更 → 「編集中のテーマでお店を更新」

※ ログイン情報はこのバックアップに含まれない。
