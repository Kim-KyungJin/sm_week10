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
   
   
### 위치정보 입력 & 세부 비용 설정 함수 추가(김경진, 홍수빈)   
>1. 위치정보 입력 spinner 추가   
>>
>>크게 시/도로 구분하여 상위 지역구/ 하위지역구 두 개의 값을 spinner로 선택하여 가게의 지역구를 설정할 수 있습니다.   
>>![KakaoTalk_20210510_170742185](https://user-images.githubusercontent.com/76034369/117631083-d889b600-b1b6-11eb-8d24-6494fda7eaf5.jpg)   
>

>
>('도' string_array)   
>>![20210510_171715](https://user-images.githubusercontent.com/76034369/117628029-ab87d400-b1b3-11eb-96b1-f05c0be34784.png)   
>>

>('시'string_array/ 대표로 부산만)   
>>![20210510_171734](https://user-images.githubusercontent.com/76034369/117628219-de31cc80-b1b3-11eb-937d-a4a940593f6c.png)   
>>

>>
>>
>> 이중 spinner를 만들어 '서울' 선택시 -> 서울 세부 지역/ '경기' 선택시 -> 경기 세부 지역의 리스트가 보여지는 함수를 만들었습니다.   
>> ![KakaoTalk_20210510_171046943_01](https://user-images.githubusercontent.com/76034369/117628336-fdc8f500-b1b3-11eb-8c7b-90cdace4d1c6.jpg)   
>>![KakaoTalk_20210510_171046943](https://user-images.githubusercontent.com/76034369/117628342-fefa2200-b1b3-11eb-8356-4c666eef5063.jpg)   
>>

>2. 세부 비용 설정 함수 추가   
>>저희 어플은 전체 비용을 입력 후 추천 모드, 혹은 셑프 설정을 통해 식당, 카페, 쇼핑, 주점, 기타 비용을 비율에 따라 나눈 후 나눠진 비율에 맞는 가게를 추천해줍니다.   
>>그렇기 때문에 비용을 각 장소별로 나누어 줄 필요가 있는데 추천 모드는 '식당 위주', '쇼핑 위주', '주점 위주' 등의 선택에 따라 나누어 집니다.   
>>예를 들어 50000원을 입력 후 '식당 위주'모드를 선택하게 된다면 식당위주 모드는 "식당 5 : 카페 2 : 기타 3"로 설정 되어있기에(선택 창 밑에 각 모드 별 비율 설명을 보여줍니다.) 5만원 중 2만 5천원을 식비, 만원은 카페 비용, 만오천원은 기타(노래방, 이색카페 등)의 비용으로 자동 분배됩니다.   
>>후에 이 분배된 금액을 기준으로 데이터베이스에서 조건이 일치하는 가게를 추천해줍니다.   
>>
>>아래는 이 함수의 일부 입니다.   
>>금액과 모드 설정 후 확인 버튼을 누르면 입력된 값과 선택된 모드의 금앱 비율에 따라 각 금액을 계산한 후에 cost_array에 index 0부터 식당, 쇼핑, 카페, 주점, 기타 의 순으로 입력됩니다.   
>>이 array를 다음 엑티비티에 전송하여 텍스트로써 출력하는 함수까지 작성했는데, 전환된 엑티비티에서 버그가 발생하는지 튕기는 문제가 생겨 실행을 해보지 못 했습니다.   
>>![20210510_172931](https://user-images.githubusercontent.com/76034369/117629630-51880e00-b1b5-11eb-8c8c-c698ea47a1bf.png)   
>>
>>하지만 중단점을 이용하여, cost_array에 정상적으로 각각의 비용의 값이 담기고 있는 것을 확인하였습니다.(위에서 설명한 예시와 동일하게 5만원+식당우선 모드)   
>>![20210510_173830](https://user-images.githubusercontent.com/76034369/117630855-9496b100-b1b6-11eb-9a8a-fb7bc87e116e.png)   
>>
>>다음 주차에는 각각의 비율을 유저가 일일이 설정 할 수 있는 '상세 설정' 기능을 추가하고 지금 버그가 나서 실행에 실패한 부분을 수정할 예정입니다.   
>>

>3. 게시판 업로딩 오류   
>>게시판 기능을 테스트 해보려고 실행을 해봤는데 로딩 화면만 뜨고 데이터베이스에는 아무런 내용이 올라가지 않는다는 것을 확인했습니다.   
>>더불어 앱에서도 이 이후에 아무런 액션이 없는 걸로 보아 데이터베이스에 값을 넘겨줄 때 오류가 나는 것 같습니다.   
>>![KakaoTalk_20210510_192852567](https://user-images.githubusercontent.com/57963888/117650822-2957d980-b1cc-11eb-8f1c-12e710811578.png)
>>![KakaoTalk_20210510_192852982](https://user-images.githubusercontent.com/57963888/117650832-2a890680-b1cc-11eb-837a-094990b92469.png)   
>>![KakaoTalk_20210510_192854443](https://user-images.githubusercontent.com/57963888/117650835-2b219d00-b1cc-11eb-8997-bcdbb6e0b560.png)
>>![KakaoTalk_20210510_192855069](https://user-images.githubusercontent.com/57963888/117650842-2bba3380-b1cc-11eb-87db-b19e1bac428a.png)   
>>




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
>> 변경된 이름과 비밀번호 값은 회원가입할 때 처럼 HashMap형태로 데이터베이스에 updateChildren()해줍니다.
>> 비밀번호 변경은 파이어베이스에서 제공하는 updatePassword() 함수를 사용했습니다.
>> 다음은 그 코드입니다.
>> 
>>![정보수정](https://user-images.githubusercontent.com/79883808/117541668-d6591780-b04f-11eb-9d6b-2cfee23717de.PNG) 
>>
>> 다음은 그 실행영상입니다.
>> 변경된 비밀번호로 정상 로그인된 것을 확인할 수 있습니다.

>>[사용자 정보 수정](https://user-images.githubusercontent.com/79883808/117540396-30ef7500-b04a-11eb-9436-ee0933aa4f34.mp4)

>> 2. 가게 정보 수정   
>> 
>> 가게 이름, 주소, 영업시간 정보를 수정하는 기능으로 데이터베이스에 데이터를 수정하는 것까지를 목표로 했습니다.
>> 이번주는 수정하는 기능만 구현만 한 것으로 가게 정보 수정의 완성본은 아닙니다.
>> 
>> 우선 가게 정보가 저장되어 있는 StoreInfo 데이터베이스를 만들어 주었습니다.
>> 사용자마다 부여되었던 uid를 key값으로해서 회원가입할 때 StoreInfo에 저장됩니다.
>> 아직 가게 정보를 입력받을 시점을정하지 않아 데이터가 비어있는 상태로 저장되며 이는 이번주에 팀원들과 상의 후에 적용할 계획입니다.
>> 일단은 가게 데이터가 비어있을 시에 정보 수정을 사용하면 데이터가 저장되게 하였습니다.
>> StoreInfo도 User DB와 마찬가지로 uid로 사용자를 구별하며 안에는 가게 이름, 주소, 영업시간에 대한 정보가 저장됩니다.
>> 주소 정보는 저희들의 실력부족으로 세세하게 입력받기 힘들 것 같아서 크게 시,도와 상세주소 정도로 입력받기로 하였습니다.
>> 
>> 이번주는 가게주 layout(이번주 홍수빈, 김경진의 1번 참고)이 완성되기 전이었으며, 데이터베이스에 저장하고 수정하는 것을 목표로 하였기 때문에 일반 사용자의 layout을 이용하였고 정보 값도 EditText로 입력받아 저장되게 하였습니다.
>> 다음주에는 수정된 Spinner로 입력된 데이터를 DB에 저장되게 할 계획입니다.
>>
>> 다음은 지금까지의 실행영상입니다.

>> [가게 정보 수정](https://user-images.githubusercontent.com/79883808/117651551-07128b80-b1cd-11eb-9296-cc41d05a1c5f.mp4)

>> 다음은 가게 정보가 비어있을 때의 수정하기 실행영상입니다.

>> [가게 정보가 비어있을 시](https://user-images.githubusercontent.com/79883808/117654737-23b0c280-b1d1-11eb-9dcb-5fc2a9279271.mp4)

>> 3. 이미지 업로드
>> 
>> 업주들이 사용할 layout에서 자신들의 가게를 등록할때 필요한 사진들을 갤러리에서 불러오는 기능을 구현했습니다. 
>> 아직 업주창들이 만들어지지 않은 상태이기 때문에 새 layout 과 activity를 만들어 기능 구현이 가능한지만 확인 하였습니다. 
>> 
>>![buttonclick](https://user-images.githubusercontent.com/79883558/117652006-9a4bc100-b1cd-11eb-85c9-bed80d8b438a.png)
>>
>> 사진을 고르고 업로드 할 수 있는 버튼 두개와 갤러리에서 가져오는 사진을 볼 수 있는 이미지뷰를 사용하였고 choose버튼을 클릭하면 갤러리에 가서 이미지를 가져올 수 있게 하였고 upload버튼을 누르면 이미지가 사용하고 있는 파이어 베이스에 업로드가 되게 하였습니다.
>> 
>>![upload](https://user-images.githubusercontent.com/79883558/117652298-f6aee080-b1cd-11eb-851b-cfe87ce69fe5.png)
>>
>> 지정한 경로 (파이어베이스 스토리지)에 갤러리에서 가져온 사진들이 업로드에 관한 코드입니다.
>> 
>> 버튼을 누르고 갤러리에서 이미지를 가져오는거 까지는 실행이 되나 그 사진이 파이어베이스에 올라가지 않는 오류가 나서 수정해야 합니다.
>> 일단 구현이 가능한 부분까지 실행한 영상입니다. 

>>https://user-images.githubusercontent.com/79883558/117652803-953b4180-b1ce-11eb-92e3-2c4d3e8d6f57.mp4

>>

### (이준석, 미르자크메더브 사르더르)   
