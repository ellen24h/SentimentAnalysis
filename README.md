# Sentiment On
: Sentiment Analysis Server (input: sentence, output: sentiment value)

- Sentiment On은  
	- 1)사용자의 감정을 문장의 형태로 입력받아, 
	- 2)`감정 점수`와 `감정을 나타내는 단어`를 json 형태로 return해주는 
	- 3)NodeJS 기반의 Web Server입니다.

- 감정분석에 사용된 기술
	- 2477개의 words와 phrases가 등록되어 있는 `AFINN-111`을 기반으로 한 Open Source Library인 `Sentiment.js`를 사용하였습니다.
		- `AFINN-111` : AFINN is a list of English words rated for valence with an integer
between minus five (negative) and plus five (positive). The words have
been manually labeled by Finn Årup Nielsen in 2009-2011. 
		-  `Publish`: Informatics and Mathematical Modelling, Technical University of Denmark	
		-  `AFINN-111 Link`: http://www2.imm.dtu.dk/pubdb/views/publication_details.php?id=6010
		- `Sentiment.JS Link` : https://github.com/thisandagain/sentiment 
- 사용 방법
	- on.ellenseon.net/sentiment?sentence=helloworld 와 같은 방식으로 요청을 보냅니다. (GET 요청)
	- OnstagePlayerServer에서 해당 문장을 받아서, parameter로 sentiment를 돌린 결과값을 json 형태로 return해 줍니다.

- 문의사항이 있으면 seunghyeon.seon@navercorp.com 으로 mail 주시기 바랍니다.

- - -

### 구현 Note

- server-app balance를 어떻게 할 것인가?
	- server의 역할을 최소로 

- 서버에서 어떤 역할을 할 것인가?
	- 1) App에서 sentence을 보내면,
	- 2) sentence를 분석해서 sentiment value를 도출한다.
	- 3) sentiment value를 return 해준다.

- sentiment value / color / playlist는 app에서 관리

- 어떻게 sentence를 보내고 받을것인가?
	- 일단 http 통신
	- RESTful하게 하면 좋지 않을까?

- 순서
	- on.ellenseon.net/sentiment?sentence=helloworld와 같은 방식으로 요청을 보낸다. (GET 요청)
	- 문장을 받아서, parameter로 sentiment를 돌린 결과값을 json 형태로 return해준다.

