# Note
2022 9/7일
\n : 0a<-16진수로
I/O : Input/OutPut
파일 불러오기
핸들 = open(파일명,모드)filename.txt , 'r' 예를들어 r(리드모드)는 디폴트 모드(읽어오기) 'r'을 생략할경우 읽어 오겠다 자동지정
full path : 전체경로를 의미함 ★★★★★★★★★★★★★★★★★★★★★★★★★★★★★★★★
● 읽기용으로 열린 파일 핸들은 파일의 각 줄에 대한 문자열의 시퀀스로 볼수있음
● for 문을 사용하여 시퀀스를 반복하여 돌 수 있음
● 시퀀스는 정렬된 집합이다

#===========================================================================================================================
과제 : Text File 만든후
한줄씩 읽어서 file 전체의 단어를 분리하고 겹치는 단어를 나타내는 pict를 출력하시오


def Main2():
    for s in str1:
        s1 = s.split(" ")
        MakeDict(s1)
    print(sDict)
def Main():
    xFile = open("Test.txt")
    for x in xFile:                 #텍스트 파일에서 한줄씩 읽어온다
        x1 = x.split(" ")
        MakeDict(x1)
    print(sDict)
        
Main()



#=======================================================================================================
파일 전체를 읽을수있는 read 함수
fhand = open('mbox-short.txt')
inp = fhanc.read()
print(len(inp)

#=======================================================================================================
9월 13일 화요일
try 와 except

try:
	예외가 발생할 수 있는 코드
except:
	예외 발생시 실행하는 코드

문제
KBD 에서 문자열을 입력받아 숫자로 변환하는 프로그램을 작성하시오 단 입력오류시 다시 입력 가능하도록 구성하시오

while True:
    s = input("숫자형 문자를 입력하세요")
    try:
        i = int(s)
        print(i)
    except:
        try :
            j = float(s)
            print(j)
        except :
            print("잘못 입력하셧습니다.")
            break
	    
	    
	    
--------------------------------------------------------------------------------------------------------------------------------------	    
2022년 9월 14일

s = ["길동","길순","길주"]
for i in range(len(s)) :
    print(s[i])           #i 만 출력하였을 경우 0,1,2 len 에 의해 요소값만 출력
                            #s[i] s에 i를 리스트로 넣어 출력할경우 이름순으로 출력이 된다

for name in s :         #위와 같은 결과값
    print(name)




read 읽는 함수[파일을 불러올떄 사용] 예를들면 open("Test.txt",mode = "r" <----r이 리드 읽기 준비 라고 이해 / 'w' 쓰기<----
rb <---- 바이너리 모드



---------------------------------------------------------------------------------------------------------------------------
@@@@@@ 파일을 불러와 나열

#f = open("test.txt") # file 'test.txt' 를 읽기 전용 모드로 open. 단, text mode.로 읽어온다
#for ln in f :               # f를 문자열 리스트처럼 사용 하여 한 라인씩 Read
#    print(ln)
#---------------------------------------------------------------------------------------------------
#읽어온 한 라인을 문자 단위로 하나씩 출력하세요.
#단 16진수로 표기 하세요. "%02x"%c

f = open("test.txt")                # file 'test.txt' 를 읽기 전용 모드로 open. 단, text mode.로 읽어온다
fr = f.read()                       #f 로 불러온 text 파일을 read를 사용하여 한 문장으로 바꾸어준다(처음부터 끝까지 읽어라)
frt = fr.split("\n")                #read를 이용하여 불러온 파일을 \n 기준으로 스플릿하여(나누어)낸다
for i in range(len(frt)):           # 
    if i <9 :                       #1번 부터 9번까지는 실제로 0이 안붙은 1,2,3,4,5 로 프린트 되어 지기 때문에 0번을 같이 프린트 하여 나타내어 준다
        print(f'0{i+1} : {frt[i]}')
    else :
        print(f'{i+1} : {frt[i]}')


#---------------------------------------------------------------------------------------------------
#교수님 풀이
f = open("test.txt")
i = 1
buf = f.read()
b = buf.split('\n')
for ln in b :
    print(f"{'%3d'%i} : {ln}\n",end = "")
    i = i + 1

    for c in ln :
        c1 = ord(c)                                          #단일 문자(열)을 16진수로 바꾸어 주어 c1에 반환하여 준다
        print(f"{'%02x'%c1}", end=' ')                   #end=''는줄바꿈  %02x 는 16진수를 2자리로 표시함 02는 두자리수의 16진수를 채워주는데 앞이 비어있다면 0을 채워준다
    print("\n")                                                                 #%c 는
 


#=======================================================================================================================
#점 그래프

install.packages("mlmRev")

getwd()
setwd("c:/bigdataR")
library(lattice)
library(mlmRev)
str(Chem97)
head(Chem97)

help("histogram")

histogram(~gcsescore | score, data = Chem97) #첫번째 결과 그래프

histogram(~gcsescore | factor(score), data = Chem97)

densityplot(~gcsescore | factor(score), data = Chem97,
            groups = gender,
            plot.points = T, auto.key = T)

help(barchart)
help(VADeaths)
str(VADeaths)
head(VADeaths)
summary(VADeaths)
VADeaths
dft <- as.data.frame.table(VADeaths)    #table 빈도수를 나타낸다
dft

barchart(Var1 ~ Freq | Var2, data = dft, layout = c(4,1), origin=0)


help(dotplot)
dotplot(Var1 ~ Freq | Var2, data = dft, layout = c(4,1))
dotplot(Var1 ~ Freq, data = dft, groups = Var2, type="o", auto.key = list(space = "right", points = T, lines = T))
#dotplot 차트에 선을 연결 할수있다 선을 연결하기 위해서는 나누어 진 그래프를 하나로 합쳐야 한다


#=====================================================================================================================
#산점도 그래프
library(datasets)
str(airquality)
xyplot(Ozone ~ Wind, data = airquality)
xyplot(Ozone ~ Wind | factor(Month), data = airquality, layout=c(5,1))

head(quakes)
#xyplot(lat ~ long, data = quakes, pch=".", main = "1964")

tplot <- xyplot(lat ~ long, data = quakes, pch=".")
tplot <- update(tplot, main="1964년 이후 지진 위치")
tplot
print(tplot)

head(quakes)
range(quakes$depth)
summary(quakes$depth)
quakes$depth2[quakes$depth >=40 & quakes$depth <=150] <- 1
quakes$depth2[quakes$depth >=151 & quakes$depth <=250] <- 2
quakes$depth2[quakes$depth >=251 & quakes$depth <=350] <- 3
quakes$depth2[quakes$depth >=351 & quakes$depth <=450] <- 4
quakes$depth2[quakes$depth >=451 & quakes$depth <=550] <- 5
quakes$depth2[quakes$depth >=551 & quakes$depth <=680] <- 6
head(quakes) #6단계로 나누어 놓은 데이터 자료 #핵터를 사용하여 범주형으로 바꿀수있다

#xyplot(lat ~ long | depth2, data = quakes, pch = ".")        #팩터 함수를 사용하지 않은 상태
xyplot(lat ~ long | factor(depth2), data = quakes, pch = ".") #팩터를 사용하여 범주형으로 바꾸어줌

head(airquality)

xyplot(Ozone + Solar.R ~ Wind | factor(Month), data = airquality, col = c("blue","red"), layout=c(5,1))

numgroup <- equal.count(1:150, number = 4, overlap = 0)
numgroup

depthgroup <- equal.count(quakes$depth, number = 5 , overlap=0)
depthgroup

xyplot(lat ~ long | depthgroup, data = quakes, pch = ".")

range(quakes$mag)

magnitudegroup <- equal.count(quakes$mag, number = 2, overlap = 0)
magnitudegroup

xyplot(lat ~ long | magnitudegroup, data = quakes,
       main = "fiji Earthquakes(msgnitude)",
       ylab = "latitude", xlab = "longitude",
       pch = "o", col = "red")
       
       
       
       
       
   ==============================================================================================================================================
   
class point : # 2D point (2차원 포인트) x 와 y 축을 나타
    x = 0
    y = 0

    def __init__(self,x=0 , y=0):
        self.x = x
        self.y = y

    def __add__(self, p) : #p : point class 객채
        x1 = self.x + p.x
        y1 = self.y + p.y
        return (point(x1,y1))
    
    def Scalar(self, m) : #m : 실수
        x1 = self.x * m
        y1 = self.y * m
        return(point(x1,y1))
    
    def __mul__(self, p) :
        x1 = self.x * p.x
        y1 = self.y * p.y
        return(point(x1,y1))

p1 = point(10,10)
p2 = point(20,20)
p3 = p1+p2
p4 = p1*p2
p5 = p1.Scalar(50)
print(f"(10,10) + (20,20) = ({p3.x},{p3.y})")
print(f"(10,10) * (20,20) = ({p4.x},{p4.y})")
print(f"(10,10) * 50        = ({p5.x},{p5.y})")
print(f"(10,10) + (20,20) = ({p3.x},{p3.y})")


#===========================================================================================================================================
변수는 메모리에 할당된 

객체 클레스와 인스턴스

https://donutsoft.co.kr/ 도넛소프트 사이트 <--- 강의온 대표님 회사 주소



 https://jdk.java.net/archive <---- java 다운로드 주소
-> 11GA 버전 다운 

https://www.mariadb.com/   <-------mariadb 다운로드 주소
-> 다운로드 -> 10.6.10-ga 안정화 버전 -> MS Windows 변경
utf8 설치시 클릭 

접속 명령어 : mysql -u root -p
설치시 지정했던 비밀번호 입력

마리아 빠져나오는 키 quit


https://www.mysql.com/
->MySQL Community Downloads -> connector -> Archived -> 5.1.49버전 ->  Platform Independent (Architecture Independent), ZIP Archive




======================================================================================================================================================
# code 가 6 단가 20만원인 "청소기" 2개를 추가
query = "insert into goods2 values(6, '청소기', 2, 200000)"
dbSendUpdate(conn, query)

# 단가 60만원 보다 큰 상품에 대해 수량을 5로 수정
query = "update goods2 set su = 5 where dan > 600000"
dbSendUpdate(conn, query)

# 수량이 1인 상품을 삭제
query <- "delete from goods2 where su = 1"        #특정 코드 내용을 삭제 한다
dbSendUpdate(conn, query)

# 각 문법이 실행될 때마다 전체 테이블 조회
query <- "select * from goods2 wher name like '%기' "   #%는 모든 문자를 말하고 마지막은 기 <--- 가와야 한다

# 일부 열의 데이터만 추가
query <- "insert into goods2 (code, name, su, dan) values(7, '안마의자' , 1, 500000)"

# DML(Data Manipulatlon Language) : 데이터 조작어
# select, insert, update, delete
# select 필드명리스트 from 테이블명 where 조건절 order by 정렬키 순서
# insert into 테이블명 (필드리스트) values(값리스트)
# update 테이블명 set 필드명1 = 값1, 필드명2= 값2........ where 조건절
# delete from 테이블명 where 조건절



↓↓↓↓↓ SQL 사용방법

USE WORK;
SELECT * FROM shopuser;

DESC shopuser;
INSERT INTO shopuser VALUES ('tiger', '홍길동', 25);
INSERT INTO shopuser VALUES ('lion', '김삿갓', 30);

DESC shopproduct;
INSERT INTO shopproduct VALUES (1, '냉장고', 1000000);
INSERT INTO shopproduct VALUES (2, '세탁기', 550000);
INSERT INTO shopproduct VALUES (3, 'TV', 1200000);
INSERT INTO shopproduct VALUES (4, '청소기', 200000);
SELECT * FROM shopproduct;


DESC shopsale;
INSERT INTO shopsale VALUES('tiger', 2 , 1);
INSERT INTO shopsale VALUES('lion', 3 , 2);
INSERT INTO shopsale VALUES('lion', 4 , 2);
INSERT INTO shopsale VALUES('tiger', 1 , 3);
SELECT * from shopsale;

/*  Join 쿼리 [별명을 사용하여 문법을 줄일수있다 2개의 테이블 조인 */
SELECT u.uid, u.uname,s.pCode, u.uage, s.sCount
	FROM shopuser u, shopsale s
	WHERE u.uid = s.uid;
	
/* shopProduct와 sopsale 조인 */
SELECT p.pCode, s.sCount, p.pName 
	FROM shopproduct p, shopsale s
	WHERE p.pCode = s.pCode;

/* shopuser, shopsale, shopproduct 조인 */
SELECT u.uname, p.pName, s.sCount
	FROM shopuser u, shopproduct p, shopsale s
	WHERE u.uid = s.uid AND p.pCode = s.pCode;
	
SELECT *
	FROM shopuser u, shopproduct p, shopsale s
	WHERE u.uid = s.uid AND p.pCode = s.pCode;

/* 김삿갓이 구매한 내역에 대해 성명, 상품명, 수량을 출력 */

SELECT u.uname, p.pName, s.sCount, p.pPrice * s.sCount subtot
	FROM shopuser u, shopproduct p, shopsale s
	WHERE u.uid = s.uid AND p.pCode = s.pCode
		AND u.uname = '김삿갓';

/* 서브쿼리 : 조회한 결과를 다른 조회구문의 입력 */
/* 세탁기를 구매한 고객들의 모든 이름 */

SELECT * FROM shopsale;

SELECT * FROM shopuser WHERE uid =
	(SELECT uid FROM shopsale WHERE pCode = 
		(SELECT pCode FROM shopproduct WHERE pname = '청소기')) ;





-------------------------------------------------------------------------------------------------------------------------------------------------------
테이블 만들고 계정 로그인 기타등등

로그인 방법
mysql -u (아이디적는공간) -p
비밀번호

show databases;

use test;
showtables;
createdatabase work;
show databases;
use work;

#테이블 만들기
create table goods(
	code int primary key,
	name varchar(2) not null,
	su int,
	dan int);

#테이블 목록 보기
show tables;

#레코드 추가

insert into goods values (1, '냉장고', 2, 850000);

#추가레코드 확인
select * from goods;


사용자 계정만들기
create user 'scott'@'localhost' identified by 'tiger';

사용자에게 권한주기
grant all privileges on work.* to 'scott'@'localhost';

flush privileges;

나가기
quit





#====================================================================================================================================

url <- "http://apis.data.go.kr/B552584/ArpltnInforInqireSvc/getCtprvnRltmMesureDnsty?serviceKey=SyDxU1fZhs5bxdV3Uy9pwqEIgdmXRFEedsH0fdk52etyVn9pTU1zqj4Apm0aMHNXAfTCoXMNoHcyxXb%2Bgjrjcw%3D%3D&returnType=xml&numOfRows=100&pageNo=1&sidoName=%EC%B6%A9%EB%B6%81&ver=1.0"

xmlFile <- xmlParse(url) #파서를 이용하여 저장
df <- xmlToDataFrame(getNodeSet(xmlFile, "//item"))   #반복탐색하며 item 내용을 저장한다
df
stationName <- df$stationName
pm10Value <- as.numeric(df$pm10Value)   #숫자형으로 변환
pm10Value
barplot(pm10Value, names.arg = stationName, col = rainbow(7))

#===================================================================================================================
#측정소별 10시간 측정정보 조회

url <- "http://apis.data.go.kr/B552584/ArpltnInforInqireSvc/getMsrstnAcctoRltmMesureDnsty?serviceKey=SyDxU1fZhs5bxdV3Uy9pwqEIgdmXRFEedsH0fdk52etyVn9pTU1zqj4Apm0aMHNXAfTCoXMNoHcyxXb%2Bgjrjcw%3D%3D&returnType=xml&numOfRows=10&pageNo=1&stationName=%EB%B3%B5%EB%8C%80%EB%8F%99&dataTerm=DAILY&ver=1.0"

xmlFile <- xmlParse(url) #파서를 이용하여 저장
df <- xmlToDataFrame(getNodeSet(xmlFile, "//item"))   #반복탐색하며 item 내용을 저장한다
df
pm10Value <- as.numeric(df$pm10Value)
lifelse(!is.na(pm10Value), pm10Value, round(mean(pm10Value,na.rm = T), 0))
dataTime <- df$dataTime
str_sub(dataTime, 12)
barplot(pm10Value, names.arg = str_sub(dataTime, 12), col = rainbow(7))

pm10Value



#=======================================================================================================================
install.packages("wordcloud")
library(wordcloud)
word <- c("서울", "부산", "대구")  #항목(문자열)
freq <- c(600, 430, 250) #빈도수(정수)
wordcloud(word, freq, random.order = F, random.color = F, colors = rainbow(12))


#전입이 많은 지역을 wordcloud 로 표현
data <- read.csv(file.choose(), header = T, fileEncoding = "euc-kr")
head(data)

x <- grep("시$", data$행정구역.시군구.별)
x
data1 <- data[ x    ,    ]
head(data1)
x <- grep("군$", data$행정구역.시군구.별)
x
data2 <- data[x,         ]
data3 <- rbind(data1, data2)
data4 <- data3[data3$순이동.명. > 0   , ] #순이동이 0보다 큰경우
word <- data$행정구역.시군구.별
freq <- data4$순이동.명.
wordcloud(word,freq, random.order = F, random.color = F, colors = rainbow(12))

df <- data.frame(지역=word, 빈도수=freq)
view(df)

install.packages("wordcloud2")
library(wordcloud2)


