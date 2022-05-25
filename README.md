# Filechain
프로그램 실행 전 자동 무결성 검증 알고리즘

## Explain
프로그램을 배포 서버에서 클라이언트까지 중간에 수정 없이 제대로 배포 되었는지 간단한 알고리즘으로 확인하는 방법이다.
이것은 따로 보안 프로그램 없이 변경되지 말아야 할 파일들의 무결성을 검증하는 기능을 담고있다.
파일체인은 블록체인 기술을 기반으로 하고 저비용 고사양을 목표로 한다.
네트워크 기능을 필수로 하고 데스크톱, 모바일, IoT, 임베디드 환경에서 사용가능 하도록 목표로 한다.

## Technology Development Background
1. CBC (Cipher-block Chaining) - integrity
2. BLAKE2 (Hash Algorithm) - fast

## Blueprint
<div><img width="500" src="https://user-images.githubusercontent.com/71743128/170218506-62a171c4-8238-4152-91a2-193506ee4455.png"></img></div></br>

```
    total: 5
    success: 3 or more
    failure: 2 or less
```
네트워크는 메시형으로 구성하고 서버는 현재 실행중인 모든 클라이언트 프로그램 정보를 필요로한다.
클라이언트는 프로그램 실행 시작시 서버 상관없이 현재 실행중인 모든 프로그램들 중 일치하는 파일체인 값의 수량이 50%만 넘으면 해당 프로그램을 실행 시킬 수 있다.

## Concept
<div><img width="230" src="https://user-images.githubusercontent.com/71743128/170222324-9cf99c7c-d65f-437d-aceb-395e9560c129.png"></img></div></br>

Now Hash는 현재 실행 프로그램의 파일 군집 해시값이고 Last Hash는 이전 파일 군집 해시값 또는 초기값이다.   
Now Hash와 Last Hash를 합쳐서 Filechain Hash라고 하고 이것이 하나의 단위가 된다.   

### Now
* 현재 단일폴더 절대경로만 사용가능

#### Developer
* Deeklming
