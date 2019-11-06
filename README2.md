# Virtualbox 설치

우분투 환경에서 virtualbox를 설치하기 위해서는 아래의 명령어를 실행한다.

```
sudo apt-get install virtualbox
```

그리고 아래의 명령어를 이용해 disk와 vboxusers그룹에 사용자 계정을 추가한다.

```
sudo usermod -a -G dist $USER
sudo usermod -a -G vboxusers $USER
```

디스크와 Virtualbox 사용자 관련과 권한을 추가하는 내용이다.<br>
아래의 사이트에 방문하여, 해당 버전에 맞는 아래의 2개 파일을 다운받는다.

> http://download.virtualbox.org/virtualbox/

- Oracle_VM_VirtualBox_Extension_Pack.vbox-extpack : 파일 중간에 버전이 포함되어 있으며, 확장 기능이다.
- VBoxGuestAdditions.iso : 파일 중간에 버전명이 포함되어 있으며, 게스트 확장 기능으로 가상 머신에서 운영체제 설치 후 설치되어져야 하는 파일.

< 아래 순서대로 진행 >

- [File] 메뉴에서 [Preference]를 선택
- Extensions 탭을 선택
- [Add new pakage] 아이콘 클릭
- 다운받은 vbox-extpack 파일을 지정해 설치

## Virtualbox 가상머신 생성

가상머신을 생성해 보도록 한다.<br>
Virtualbox 윈도우 설치를 할 것이다.

> 참고, https://hiseon.me/linux/ubuntu/ubuntu-virtualbox-install/

### Name and operating system

[New] 아이콘 클릭 후 설치하고자 할 운영체제의 기본정로를 입력

### Memory size

가상머신에서 사용될 메모리 용량을 설정

### Hard disk

가상머신에서 사용될 디스크를 설정하는 내용으로 디스크는 나중에 추가할 수도 있고, <br>
지금 바로 생성할수도 있고 기존에 존재하는 디스크를 사용할 수도 있다.

`Create a tirtual hard disk now` 선택 후 create 버튼 클릭

### Hard disk file type

디스크 유형을 선택하는 것으로 `기본 VDI`를 선택하고 Next 클릭

### Storage on physical hard disk

가상머신의 디스크 용량을 동적/고정된 사이즈로 할당할 것인지 선택하는 내용으로 기본값으로 설정<br>
`Dynamically allocated` > Next

### File location and size

디스크 이름과 용량을 설정 한 뒤에 create 클릭


## Virtualbox 가상 머신 설정

부팅 후 설치할 iso 파일을 지정해주어야 한다.

- [Settings] > [Storage] > [Empty]클릭 후 우측 아이콘 클릭 후 윈도우 설치 iso파일을 지정한다.
- [Shared Folder] 탭에서 [+] 클릭 후 공유할 디렉토리 지정
- [OK] 버튼 클릭 후 저장 


## Virtualbox 윈도우 설치

상단의 [Start] 아이콘을 클릭 해 가상머신을 실행







