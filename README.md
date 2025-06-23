# capstone-everytime-crawler

**에브리타임(Everytime)** 커뮤니티의 게시글을 크롤링하기 위한 코드이며,
학교별 커뮤니티 게시판에서 게시글의 **제목과 본문**을 수집할 수 있도록 구성되어 있습니다.

- 각 게시글은 에브리타임의 고유 URL 형식인  
  `https://everytime.kr/{게시판 번호}/v/{게시글 번호}`를 따르며,  
  `게시판 번호 + 게시글 번호` 조합이 고유 식별자(PK)로 사용됩니다.

- 수집 대상은 제목(title)과 본문(content)에 한정되며, 댓글은 포함되지 않습니다.

- 중복 게시글 제거를 위해 크롤링 시간(timestamp) 정보가 포함되어 있습니다.

- 에브리타임은 한 페이지당 20개의 게시글을 보여주며,  
  이에 따라 한 개의 `.json` 파일은 20개의 게시글 데이터를 포함하는 형태로 저장됩니다.


```json
{
    "post_link": "https://everytime.kr/123456/v/12345678",
    "title": "잉포 ㅂㅁㅎ교수님 중간고사 없어?",
    "content": "ㅈㄱㄴ\n관련해 아는거 있음 알려주라~",
    "crawled_time": "2025-04-02 13:22:40"
},
```


## Directory structure
```
├── crawler
│   ├── config.py
│   ├── crawler_util.py
│   ├── settings.py
│   └── start.py # 크롤링 실행
├── data
│   ├── load_data.py
│   └── preprocess.py
└── README.md

