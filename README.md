# Note
2022 9/7일
\n : 0a<-16진수로
I/O : Input/OutPut
파일 불러오기
핸들 = open(파일명,모드)filename.txt , 'r' 예를들어 r(리드모드)는 디폴트 모드(읽어오기) 'r'을 생략할경우 읽어 오겠다 자동지정
full path : 전체경로를 의미함
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
