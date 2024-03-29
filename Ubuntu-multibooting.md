# ubuntu 18.04 install

리눅스 배포판 중 하나인 Ubuntu 운영체제를 설치해봅니다.

- 우분투 ISO 파일 다운받기(해당 버전: ubuntu-18.04.3-live-server-amd64)
  - 이미 설치하셨다면 넘어가셔도 됩니다. 
  - iso: http://releases.ubuntu.com/bionic/ubuntu-18.04.3-live-server-amd64.iso
  
## 우분투 설치공간 마련 (기존 파티션 줄이기)

- 윈도우 > 설정 > 디스크 관리/혹은 정리
- (C:) 마우스 우클릭 > 볼륨 축소(H)
- 원하는 만큼 메가바이트(MB) 단위로 적고 축고(S)버튼 클릭
  - 남은 공간의 절반정도가 적당함 (적어도 50G 정도)
- (C:)의 공간 확보 확인 (할당되지 않음에 들어가는 기가바이트 확인)

## Window 재부팅

- 우분투 usb 를 꼽고 재부팅
- 메인보드 접속을 위해 `esc, f2, f11` 중 하나를 누름
- 메인보드 바이오스에서 부팅 순서를 정함
  - ubuntu usb 를 1번으로! 
- UEFI 펌웨어라면 `Secure Boot` 해제!
- 바이오스를 저장하고 나오면 usb 메모리로 부팅이 시작됨

### 환영합니다 창!

- 언어는 한국어로 바꾸고 Ubuntu 설치를 누름
- 와이파이 연결 필수!
- Ubuntu 설치 중 업데이트 다운로드와 그래픽 어쩌고 둘다 클릭! 후 계속
- 그래픽과 어쩌고를 누를 때 만약 Turn off Secure Boot가 추가적으로 뜬다면 앞에서 SecureBoot를 활성화 한것
 - 체크박스 풀어주고 계속
- 설치형식은 기타를 눌러주고 계속

### 파티션 할당 (Swap, 루트)

- 아래에 있는 남은 공간을 클릭하고 `+` 클릭
- 우선 S
