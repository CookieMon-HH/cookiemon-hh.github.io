

Jupyter notebook 확용법에 대해 알아보자.  

Jupyter 특징 및 실행방법  
---

특징
- 웹브라우저 기반, 다양한 표현도구  
- 실행되는 코드와 out 내역이 함께 ipynb파일로 저장된다.  
- 스마트기기에서도 접속될만큼 높은 호환성 및 접근성을 가진다.  

Jupyter notebook의 실행 방법  
- jupyter notebook 찾아서 실행  
- Power shell 창 호출 -> cd "원하는 실행 겅로 입력"  -> jupyter notebook 입력 -> 웹브라우저 창 실행  
- 이때 jupyter note 서버창은 끄면 안된다.  
- 바로 웹브라우저가 실행되지 않는다면 실행창에 떠있는 경로를 실행한다.  

Jupyter notebook 활용 방법  
---

- new file -> python3 : 파이썬 기반 새파일 생성
- 각 셀에는 여러줄의 코드가 입력 가능하다. 
- Run (shift enter) : 해당 코드 수행  
- Help - keyboard shorcut 부분을 확인하면 단축키를 확인할 수 있다.  
- Code/Markdown 변경가능 (ESC+Y/M): Martkdown을 선택한 경우 해당 셀에는 Markdown 문법을 활용하여 문서화 작업이 가능하다.  
- ESC + dd / cut : 해당 셀 삭제 
- Kernel : 현재 노트북의 코드 실행 주체이다. (파이썬 외에도 추가 언어들을 사용할 수 있다.
- Kernel 실행 : 각 셀을 실행하면 순서에 맞춰 왼쪽에 숫자가 입력된다. 
- Kernel Interrupt :  현재 실행중인 Kernel 중단 
- Kernel Restart : 메모리에 올라가있던 현재 실행되었던 정보들을 삭제한다. (다시 Run을 해줘야 해당 셀이 적용된다.) 
- Kernel Restard & Run all : 재시작과 함께 셀들을 run 해준다.  
- 이때 실행 순서는 위치로 구분하지 않고 왼쪽의 숫자의 순서에 따라 Run 된다.  
- 상단 문서명을 클릭하여 파일명을 수정할 수 있음  
