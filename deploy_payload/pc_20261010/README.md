# 10/10 プレビュー3件の本番投入候補（先方OK・高崎さんの了承の後に使う）

- chunk_sd.html … サイドバー用スロット（include_side_category）の kg-pc sd チャンクの新版。pc_20261008/chunk_sd.html の「お役立ち情報」箱を「ご注文のご案内」（フッターと同じ7項目）に置き換えただけ
- chunk_coupon.html … クーポン対象商品ページ（/SHOP/317030/list.html）上部に出すクーポンバナー3枚＋IDコピー。画像は pic-labo の kg_coupon_10000off.jpg / kg_coupon_3000off.jpg / kg_coupon_1000off.jpg（未登録。pc/img/ の同名を画像台帳に登録してから使う）。置き場所（カテゴリ説明欄か head追記JSか）は投入時に決める
- sp_menu_block_order.txt / sp_menu_block_useful.txt … スマホMENU（サイドバー用フリーエリア freeside の freeArea2）にある「ご注文のご案内」と「香典返し・弔事のお役立ち情報」の div.category。本番では2つの位置を入れ替える（配信HTMLから採取。&#12316; と CRLF に注意。freeside の原文はスロットから読み直して照合）
