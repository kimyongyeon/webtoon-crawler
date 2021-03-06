# webtoon-crawler
네이버 웹툰 크롤러


만화 콘텐츠(이미지) 크롤링
----
```shell
casperjs crawl_contents.js --id=웹툰아이디 --no=회수번호 --dst=대상경로
```
__stdout__으로 출력되는 정보
```json
{
  "title" : "해당 화의 제목",
  "rating" : "별점 (숫자)",
  "counts" : "이미지_조각_수 (숫자)"
}
```

마지막 화 정보 크롤링
----
```shell
casperjs crawl_last_episode.js --id=웹툰아이디
```
__stdout__으로 출력되는 정보
```json
{
  "title" : "해당 화의 제목",
  "rating" : "별점 (숫자)",
  "date" : "날짜 / 예:15.01.20",
  "no" : "회수번호 (숫자)"
}
```
* 목록 중 특별편, 프롤로그 등으로 인해서 제목의 회수번호랑 __no__번호랑 차이가 날 수 있음.


인기급상승 랭킹 크롤링
----
```shell
casperjs crawl_ranking.js
```
__stdout__으로 출력되는 정보
```json
{
  "rank_favorite" : ["title1", "title2", "title3", "title~10"],
  "rank_update" : ["title1", "title2", "title3", "title~10"]
}
```
* __rank_favorite__ : 인기 순 정렬
* __rank_update__ : 업데이트 순 정렬


주의사항
----
* Windows CMD에서 실행 시 __chcp 65001__설정 후 사용
* 가끔 no중 빠진 번호가 존재하는 웹툰이 있음

ToDo
----
* 웹툰 목록 크롤링
* 댓글
