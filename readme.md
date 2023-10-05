# CheckJapaneseMunicipalitiesInWikidata

Wikidata にある日本の行政区画（都道府県、市町村、東京特別区、区）のデータと総務省によるデータを比較し、一致していることを確認するための python スクリプト（jupyter notebook） です。

This is a python script (jupyter notebook) to verify integrity and consistency of Japanese municipality entries in Wikidata.
The list of municipalities shall be compared to the true list, retrieved from the Ministry of Internal Affairs and Communications.

## 履歴

| 日付 | 変更内容 |
| --- | --- |
| 2023-10-01 | 新規作成。都道府県、市、区までチェック。 |
| 2023-10-03 | すべての自治体を一括でチェック。 |
| 2023-10-03 | 市、特別区、区、町、村をそれぞれチェックするようにした。 |
| 2023-10-04 | 政令指定都市、市区町村、郡のチェックを追加。 |
| 2023-10-05 | 中核市のチェックを追加。 |

## 確認した内容（2023/10/4 現在）

| 種類 | アイテムコード | 確認された正しい数 |
| --- | --- | --- |
| 日本の市 | Q494721 | 792 |
| 日本の特別区 | Q5327704 | 23 |
| 日本の区 | Q137773 | 175 + 2024年区統合予定の浜松市の2新区 = 177 |
| 日本の町 | Q1059478 | 743 |
| 日本の村 | Q4174776 | 183 + 北方領土の6村 = 189 |
| 政令指定都市 | Q1749269 |  20 |
| 市区町村 | Q1054813 | 1741 + 北方領土の6村 = 1747 |
| 郡 | Q1122846 | 307（北海道は除く）|
| 中核市 | Q1137833 | 62 |

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

