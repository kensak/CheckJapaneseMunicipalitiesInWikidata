# CheckJapaneseMunicipalitiesInWikidata

Wikidata にある日本の行政区画（都道府県、市町村、東京特別区、区）のデータと総務省によるデータを比較し、一致していることを確認するための python notebook です。

## 履歴

| 日付 | 変更内容 |
| --- | --- |
| 2023-10-01 | 新規作成。都道府県、市、区までチェック。 |

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

