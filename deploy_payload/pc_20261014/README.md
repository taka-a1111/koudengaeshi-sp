# 10/14 本番投入（先方OK 10/14 11:08・高崎さん了承 10/14）

- head_coupon.txt … head追記（include_head_tag_js）末尾に足すブロック。/SHOP/317030/（クーポン対象商品）のときだけ、カテゴリ説明の section の直後にクーポンバナー3枚（kgcp）を差し込み、クリックで ID をコピー。中身は pc_20261010/chunk_coupon.html と同じ（CSS・HTML・コピー処理）。カテゴリ説明欄（先方の文章）は触らない
- サイドバー（include_side_category の sd チャンク）は pc_20261010/chunk_sd.html に置き換え。変更前は pc_20261008/chunk_sd.html
- スマホMENU（freeside freeArea2）は「ご注文のご案内」と「香典返し・弔事のお役立ち情報」の div.category を入れ替え。変更前の freeArea2 全文は高崎さんの手元のバックアップ
- 切り戻し: head追記から kg-coupon 2026-10-14 start〜end を削除／sd チャンクを pc_20261008 版に戻す／freeArea2 の2ブロックを元の順に戻す。それぞれ公開（テーマ系は「編集中」、freeside は「利用中」）
