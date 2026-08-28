# 本番実装キット（ちとせ屋SP改装・2026-08-28）

新規チャットでの再開手順。詳細な背景は handover-koudengaeshi-v10.md と SKILL_shopserve_ver3_0.md を併読。

## 0. 展開

このzipを /home/claude/kg/ に展開（payload/ と scripts/ が deploy/ 配下に入る構成）。
GitHubトークン設置:
```
# トークンは handover-koudengaeshi-v10.md（手元保管）を参照して /home/claude/.gh_token に設置
```

## 1. 実行順

| 順 | コマンド | 何をするか | 成功条件 |
|---|---|---|---|
| 1 | `python3 deploy/scripts/step1_freearea.py` | freetop body5（regist5()直呼び）と headfooter f_banner へ追記保存 | 両方「OK: 旧長→新長」表示。マーカー再読込確認込み |
| 2 | `python3 deploy/scripts/step2_theme.py` | head追記・ヘッダ・フッタの3スロットへ追記保存 | 3スロット「OK」 |
| 3 | `python3 deploy/scripts/step3_publish.py` | 更新画面へリンク経由で到達しボタン一覧を表示（**押さない**） | ボタン文言を目視確認 |
| 4 | step3のコメントを外すか手動evaluateで「**利用中のテーマ**で更新」→「**編集中のテーマ**で更新」の順に押す | 公開 | エラーなし |
| 5 | `python3 deploy/scripts/step4_verify.py` | スクロール付き本番実測＋フルスクショ | kg全表示・legacy全非表示・ranks先頭4件がNo.1〜4・imgbad0・JSerr0 |
| 6 | シンゴさん実機確認 → 完了報告送信（文面はhandover v10の11章） | | |

- 各スクリプトは冪等（マーカー既存ならスキップ）。途中で落ちたら同じスクリプトを再実行してよい。
- step3で「お店ページの更新へ」に到達できない／ボタンが無い場合はeditor権限の制約。**最後の公開ボタンだけシンゴさんが管理画面で押す**（利用中→編集中の順）。

## 2. 検証の要点（step4）

- ranks: 先頭4件の no が No.1〜No.4、hide=false。5件目以降 hide=true。→ リハーサルで疑義のあった「No.1/2が出ない」現象の最終確認ポイント
- No.2のシルバーは #8E9AA3（デモ現行値）。クライアント判断待ちの案Aは #AFB8BF
- live_after.png を必ず目視（ご挨拶・送料無料説明・商品紹介の3ブロックは旧デザインのまま残るのが正しい）

## 3. 異常時

`python3 deploy/scripts/rollback.py` → 全枠のマーカー以降を削除保存 → 公開ボタン両方を押して復旧。
完全復元が必要な場合は GitHub taka-a1111/koudengaeshi-sp の deploy_backup/*.json から該当textareaへ貼り戻す。

## 4. ファイル構成

- payload/head_append.txt … head追記末尾へ（{literal}済・media768px・非表示CSS・ランキング整形・JS）
- payload/chunk_hdr.html … include_header_shop 末尾へ
- payload/chunk_catprice.html … freetop body5 末尾へ
- payload/chunk_flow.html … headfooter f_banner 末尾へ
- payload/chunk_foot.html … include_footer_shop 末尾へ
- scripts/_common.py, step1〜4, rollback.py
- 注入マーカー: `<!-- kg-sp 2026-08-28 -->`（検索・削除の基準点）
