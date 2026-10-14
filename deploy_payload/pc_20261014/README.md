# 10/14 本番投入（先方OK 10/14 11:08・高崎さん了承 10/14）

- head_coupon.txt … head追記（include_head_tag_js）末尾に足すブロック。/SHOP/317030/（クーポン対象商品）のときだけ、カテゴリ説明の section の直後にクーポンバナー3枚（kgcp）を差し込み、クリックで ID をコピー。中身は pc_20261010/chunk_coupon.html と同じ（CSS・HTML・コピー処理）。カテゴリ説明欄（先方の文章）は触らない
- サイドバー（include_side_category の sd チャンク）は pc_20261010/chunk_sd.html に置き換え。変更前は pc_20261008/chunk_sd.html
- スマホMENU（freeside freeArea2）は「ご注文のご案内」と「香典返し・弔事のお役立ち情報」の div.category を入れ替え。変更前の freeArea2 全文は高崎さんの手元のバックアップ
- 切り戻し: head追記から kg-coupon 2026-10-14 start〜end を削除／sd チャンクを pc_20261008 版に戻す／freeArea2 の2ブロックを元の順に戻す。それぞれ公開（テーマ系は「編集中」、freeside は「利用中」）

## 実施記録（10/14）
- 保存: freeside body3（6,246字のまま。2ブロック入れ替え）、include_side_category 9,395→9,287字、include_head_tag_js 231,986→236,846字（kg-coupon 2026-10-14 start〜end を末尾に追加）
- 画像台帳: kg_coupon_10000off.jpg / kg_coupon_3000off.jpg / kg_coupon_1000off.jpg（フリーページ画像 24123）。公開URLで pc/img/ の原本とバイト一致
- 公開: 「編集中のテーマでお店を更新」2026/10/14 13:42:10。freeside もこれで反映された（「利用中」は押していない）
- 実測: PC 1280/1440/1920・スマホ 336/390 でクーポン3枚表示、JSエラー0、横はみ出し0、クリックでクリップボードに ID が入ることを確認
- 変更前の各スロット全文は高崎さんの Chrome の localStorage（kanri6.shopserve.jp）kgbk_20261014_freeside / kgbk_20261014_include_side_category / kgbk_20261014_include_head_tag_js
