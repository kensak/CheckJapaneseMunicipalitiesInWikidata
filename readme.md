# CheckJapaneseMunicipalitiesInWikidata

Wikidata にある日本の行政区画（都道府県、市町村、東京特別区、区）のデータと総務省によるデータを比較し、一致していることを確認するための python スクリプト（jupyter notebook） です。

This is a python script (jupyter notebook) to verify integrity and consistency of Japanese municipality entries in Wikidata.
The list of municipalities shall be compared to the true list, retrieved from the Ministry of Internal Affairs and Communications.

## 履歴

| 日付 | 変更内容 |
| --- | --- |
| 2023-10-01 | 新規作成。都道府県、市、区までチェック。 |
| 2023-10-03 | すべての自治体を一括でチェック。 |

## 確認した内容（2023/10/03現在）

* 「日本の特別区（Q5327704）」の要素が実際の特別区と一致。
* 「日本の区（Q137773）」の要素が実際の区と一致。
* 「日本の町（Q1059478）」の要素が実際の町と一致。
* 「日本の村（Q4174776）」の要素が実際の村と一致。
* 「日本の市（Q494721）」の（直接または間接的な）要素が実際の村と一致。
    間接的な要素を入れているのは、次のように間接的にのみ「日本の市」に含まれている市が多数あるため。
    山形市 ∈(P31) 中核市 ⊂(P279) 日本の市
    所沢市 ∈(P31) 特例市 ⊂(P279) 日本の市

ただし廃止日（P576）があるものは比較対象に含まない。

## 行政区画データについて

* 行政区画
   総務省「都道府県コード及び市区町村コード」（令和5年4月1日更新）
   https://www.soumu.go.jp/denshijiti/code.html
* 市区町村数
   J-LIS 都道府県別市区町村数一覧
   https://www.j-lis.go.jp/spd/code-address/kenbetsu-inspection/cms_11914151.html

## Wikidata の SPARQL サーバーについて

Wikidata は [RDF](https://ja.wikipedia.org/wiki/Resource_Description_Framework) というメタデータのデータモデルを記述するための枠組みに対応しており、[SPARQL](https://ja.wikipedia.org/wiki/SPARQL) という RDF 問い合わせ言語で検索ができる。

* [ウィキデータ:SPARQLチュートリアル](https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial/ja)
* [Wikidata:SPARQL query service/queries](https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries)
* [SPARQL query examples](https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples/ja)

