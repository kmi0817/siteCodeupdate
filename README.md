# siteCode update 버전

1. 설치 내용
```
pip3 install paramiko
pip3 install requests
```

2. SFTP 폴더
```
1) provider SFTP 경로: /repo_list/provider
2) consumer SFTP 경로: /repo_list/consumer
```

3. 사용자에 따라 변경 가능해야 하는 내용
- SFTP 포트, 아이디, 비밀번호, 경로 (모두 routes.py 파일에서 수정 가능)

4. 수정할 내용
- (1)
- Researcher가 선택한 데이터를, Provider의 SFTP에서 Consumer의 SFTP로 넘기기 전 credential (암호화) 과정
- 암호화에 필요한 함수를 외부 모듈로 생성하고자 함 (security.py 내에)
- 하지만 외부 모듈로 불리한 후 routes.py 에서 import 하니 오류 발생
- 원인 파악X -> 일단 routes.py 파일 내에 함수를 입력함
- (2) provider한테 credential 제시하는 페이지에서 radio로 cred_ex_id 출력하기 (리스트로 radio option 넣어야 하는데 안 됨)
- (3) researcher가 provider한테 credential 제시할 때 어떤 swagger API 사용하는지? 아님 그냥 로컬 세션 스토리지 사용하는지? 일단 아무것도 안 하고 버튼만 누르면,,, 그렇게 됨.