# 네이버/카카오에서 지역 주소 추출 프로그램 사용 방법

본 사용 방법은 실행 환경이 Mac OS임을 가정 하였습니다.

## Prerequest
### Brew 설치 
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
### jq 설치 
```
brew install jq
```

## 실행 환경 준비

### 새로운 폴더를 만들고 `get_coordinate.sh`를 해당 폴더로 이동 시킵니다.
### 터미널을 실행 시킵니다.
   처음 터미널 화면</br>
   <img width="498" alt="스크린샷 2019-07-06 오전 11 39 56" src="https://user-images.githubusercontent.com/18142295/60751006-b6d3ac80-9fea-11e9-9a8e-6a6a1f7f10a4.png"></br>

### 파일을 터미널로 드래그 합니다.</br>
![image](https://user-images.githubusercontent.com/18142295/60751070-3f524d00-9feb-11e9-956c-d6a7d8a35576.png)</br>
### 터미널에 파일 경로가 입력 됩니다</br>
  ![image](https://user-images.githubusercontent.com/18142295/60751048-0c0fbe00-9feb-11e9-9393-82cccd59292a.png)</br>
### 여기에서 `get_coordinate.sh` 부분은 지우고,</br> 나머지 부분을 이용하여 아래 명령어 예시 같이 입력해 줍니다

```
cd /Users/hekim/Documents/enbee_delivery
```

### 입력된 경로로 이동 된 것을 확인합니다</br>
![image](https://user-images.githubusercontent.com/18142295/60751062-2a75b980-9feb-11e9-9c31-0a65263ca7b9.png)</br>

## 스크립트 실행

```
./get_coordinate.sh -m [naver or kakao] -k [원하는 카워드]
```

TIP) .`/get` 을 입력하고 TAB키를 누르면 자동으로 .`/get_coordinate.sh` 가 완성 됩니다.</br>
![image](https://user-images.githubusercontent.com/18142295/60751080-5c871b80-9feb-11e9-9178-a83d77ffa8e1.png)</br>

예) Kakao map 에서 `강남역맛집` 검색

```
./get_coordinate.sh -m kakao -k 강남역맛집
```

예) Naver map 에서 `신도림역맛집` 검색

```
./get_coordinate.sh -m naver -k 신도림역맛집
```

**주의 사항**</br>
> 검색어에 `스페이스 바`는 지원하지 않습니다.</br>

**에러 발생 예**

```
./get_coordinate.sh -m kakao -k 을지로입구역 맛집
```

### 결과

### 폴더에 `{사용한 지도}_{키워드}__.json` 파일이 생성된 것을 확인합니다.

- 약 600 ~ 640 개 정도의 좌표가 저장 됩니다</br>

![image](https://user-images.githubusercontent.com/18142295/60751102-6dd02800-9feb-11e9-88c2-191321e93fc9.png)</br>

## JSON -> CSV, EXEL 파일로 변환

[https://json-csv.com/](https://json-csv.com/) 로 들어가서 결과 파일을 업로드하고 원하는 형식 파일로 다운 받으세요.
