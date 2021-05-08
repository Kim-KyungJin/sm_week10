# sm_week10
스마트모바일프로그램설계 10주차

9주차 팀 프로젝트 활동 : https://github.com/Kim-KyungJin/sm_week09

### 팀 구성   
스마트정보통신공학과 201621216 이준석   
스마트정보통신공학과 201921036 김경진   
스마트정보통신공학과 201921054 박유리   
스마트정보통신공학과 201921083 이혜정   
스마트정보통신공학과 201921104 홍수빈    
스마트정보통신공학과 201990009 미르자크메더브 사르더르    

   ***   
### 모든 항목은 변경되거나 삭제될 여지가 있습니다   
   ***   
   
   
### (김경진, 홍수빈)   

### 사용자 정보 수정, 가게 정보 수정 (박유리, 이혜정)   
>
>> 1. 사용자 정보 수정
>> 
>> 우선 수정하기 전의 사용자 정보를 보여주기 위해 데이터베이스에서 값을 읽어와 text로 출력해줍니다.
>> 다음은 그 코드입니다.
>> 
>>![사용자 정보 읽어오기](https://user-images.githubusercontent.com/79883808/117540803-d7884580-b04b-11eb-8666-42d3c22872dd.PNG)
>>
>> 이메일(아이디)은 TextView에 넣어서 수정할 수 없게 하였고 이름은 EditText에 넣어 수정할 수 있습니다.
>> 비밀번호는 입력실수로 인한 불상사가 발생하지 않게 회원가입할 때와 마찬가지로 이중확인을 받습니다.
>> 한 항목이라도 값을 입력하지 않을 시 Toast가 뜨게 하였습니다.
>> 각 항목에 값을 제대로 입력하고 변경 버튼을 누를 시 데이터베이스에 데이터와 비밀번호가 변경되고 전페이지로 이동니다.
>> 취소버튼을 누를 시에는 변경되지 않고 전페이지로 이동합니다.
>>
>> 다음은 그 실행영상입니다.   

>>[사용자 정보 수정](https://user-images.githubusercontent.com/79883808/117540396-30ef7500-b04a-11eb-9436-ee0933aa4f34.mp4)

>> 변경된 비밀번호로 정상 로그인된 것을 확인할 수 있습니다.

>> 2. 가게 정보 수정   
>> 
>> ** 가게주(업주) layout과 activity가 완성되기 전이라 일반사용자의 메인화면을 이용했습니다.**

### (이준석, 미르자크메더브 사르더르)   
