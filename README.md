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


