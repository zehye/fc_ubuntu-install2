# ubuntu 18.04 install

리눅스 배포판 중 하나인 Ubuntu 운영체제를 설치해봅니다.

- 우분투 ISO 파일 다운받기(해당 버전: ubuntu-18.04.3-live-server-amd64)
  -  iso: http://releases.ubuntu.com/bionic/ubuntu-18.04.3-live-server-amd64.iso


## 부팅 usb를 통해 Ubuntu 설치하기

- 부팅 시 F2, F11 등으로 열어서 Boot option을 해당 USB로 바꾸어 준다.
- welcome 창이 뜨면 `install Ubuntu` 로 설치를 시작

### Keyboard layout

현재 시스템에서 사용하고 있는 키보드 레이아웃을 선택. 기본 `English(US)`를 선택

### Updates annd other software

어떤 종류의 설치방식을 원하는지 선택하는 화면으로 `Normal Installation`을 선택

### Installation type

현재 하드 디스크에 설치된 운영체제가 없을 경우 해당 화면이 나타난다. 어떤 종류의 유형으로 우분투를 설치할것인지 선택하는 것으로 `Somethingelse`를 선택하여 세부적으로 파티션을 설정할 수 있도록 한다.

## 중요! 파티션 설정

> 참고1, https://hiseon.me/linux/ubuntu/install-ubuntu-18-04/ <br>
참고2, https://jeongwookie.github.io/2019/05/21/190521-ubuntu-install-usb/

위 블로그를 참고하며 아래 순서대로 진행합니다.

- **[New Partition Table] 버튼 클릭**
  - 스왑(Swap)파티션: 시스템에서 물리 메모리가 부족할 경우 사용되는 파티션. 일반적으로 메모리 용량의 2배 정도로 설정하여 생성
  - 그러나 물리 메모리 용량이 클 경우 적게 할당해도 되고 적을 경우에는 2배 이상으로 설정해도 된다 
  - Ext4 파티션: 실제 파일들이 저장되게 될 파티션.
- **Swap파티션 추가**
- **나머지 공간을 Ext4 파티션으로 나누고, 마운트 위치를 / 으로 설정**
- **생성된 파티션 내용을 확인 후 `Install Now`버튼을 클릭**
- **Continue버튼 클릭 후 진행 이어감**

### 위치 설정

지도에서 위치를 설정해준다. 

### 사용자 계정 설정

시스템에서 사용할 계정 정보를 입력

### 설치 시작

모든 설정이 완료되면, 시스템에 우분투가 설치되기 시작한다!<br>
설치가 완료되고 시스템을 재부팅하면 새로 설치된 우분투로 부팅이 된다. 


## 우분투 설치 오류 (grub-efi-amd64-signed)
 
```
The ‘grub-efi-amd64-signed’ package failed to install into /target/. Without the GRUB boot loader, the installed system will not boot.
```
해당 오류는 `grub-efi-amd64-signed`패키지가 설치를 실패했다는 내용으로 GRUB 부트로더 없이는 시스템이 부팅 할 수 없다는 내용이다.이러한 에러 메세지로 설치에 실패하였을 경우, /boot/efi 파티션을 수동으로 추가 한 다음 다시 설치해야 한다.<br>

아래는 /boot/efi 파티션에 대한 내용이다.

- 마운트 포인트 : /boot/efi
- 파티션 유형 : FAT32
- 크기 : 최소 100MB, 권장 : 200MB, 디스크의 여유가 있다면 500MB 정도면 부족하지 않을 것
- 기타 : 자동으로 파티션을 인식하지만 boot 플래그를 설정 가능하다면, 함께 설정하기


