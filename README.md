# Linked List (연결 리스트)

자료구조 linked list에 대해서 학습하는 공간입니다

## 개요

연결 리스트(Linked List)는 노드(Node)들이 연결되어 있는 선형 자료구조입니다. 각 노드는 데이터와 다음 노드를 가리키는 포인터(링크)로 구성됩니다. 배열과 달리 메모리상에서 연속적으로 저장되지 않고, 각 노드가 다음 노드의 위치 정보를 가지고 있어 동적으로 크기를 조절할 수 있습니다.

## 주요 특징

- 동적 크기 조절: 실행 시간에 노드를 추가하거나 제거하여 크기 조절 가능
- 비연속적 메모리 할당: 노드들이 메모리상에서 흩어져 있을 수 있음
- 효율적인 삽입/삭제: 중간에 데이터를 삽입하거나 삭제할 때 O(1) (위치를 알고 있을 때)
- 순차 접근: 특정 위치의 데이터에 접근하려면 처음부터 순회 필요
- 실생활 예시: 기차 칸 연결, 보물찾기 지도, 체인

## 주요 연산

### 삽입 (Insert)
- 리스트의 맨 앞, 중간, 끝에 새로운 노드 추가
- 시간 복잡도:
  - 맨 앞 삽입: O(1)
  - 맨 끝 삽입: O(n) - 단일 연결 리스트, O(1) - tail 포인터가 있을 경우
  - 중간 삽입: O(n) - 위치 탐색 + O(1) 삽입

### 삭제 (Delete)
- 리스트에서 특정 노드를 제거
- 시간 복잡도:
  - 맨 앞 삭제: O(1)
  - 맨 끝 삭제: O(n)
  - 중간 삭제: O(n) - 위치 탐색 + O(1) 삭제

### 탐색 (Search)
- 특정 값을 가진 노드를 찾거나 특정 인덱스의 노드에 접근
- 시간 복잡도: O(n)

### 순회 (Traverse)
- 리스트의 모든 노드를 방문
- 시간 복잡도: O(n)

## 구현 방법

연결 리스트는 다음과 같은 방법으로 구현할 수 있습니다:

### 1. 단일 연결 리스트 (Singly Linked List)
- 각 노드가 다음 노드를 가리키는 포인터 하나만 가짐
- 한 방향으로만 순회 가능
- 메모리 효율적

### 2. 이중 연결 리스트 (Doubly Linked List)
- 각 노드가 이전 노드와 다음 노드를 가리키는 두 개의 포인터를 가짐
- 양방향 순회 가능
- 단일 연결 리스트보다 메모리를 더 사용하지만 삭제 연산이 더 효율적

### 3. 원형 연결 리스트 (Circular Linked List)
- 마지막 노드가 첫 번째 노드를 가리킴
- 순환 구조가 필요한 경우에 유용
- 단일/이중 연결 리스트 모두 원형으로 구현 가능

## 활용 사례

실제 애플리케이션 개발에서 연결 리스트를 사용할 수 있는 구체적인 사례들입니다.

### 음악 플레이어 - 재생 목록
**앱 예시**: Spotify, YouTube Music, Apple Music
- **기능**: 다음 곡/이전 곡 재생, 곡 추가/삭제
- **구현**:
  - 각 노드가 하나의 음악 트랙을 나타냄
  - 이중 연결 리스트로 구현하여 이전/다음 곡으로 이동
  - 원형 연결 리스트로 반복 재생 구현
  - 중간에 곡을 추가하거나 삭제할 때 효율적
- **사용 시점**: 재생 목록, 플레이리스트 관리

### 웹 브라우저 - 탭 관리
**앱 예시**: Chrome, Firefox, Safari
- **기능**: 새 탭 추가, 탭 닫기, 탭 순서 변경
- **구현**:
  - 각 노드가 하나의 탭을 나타냄
  - 이중 연결 리스트로 좌우 탭 이동 구현
  - 탭 추가/삭제 시 포인터만 변경하면 되어 효율적
- **사용 시점**: 동적으로 추가/삭제되는 항목 관리

### 이미지 뷰어 - 이미지 갤러리
**앱 예시**: Google Photos, Instagram, 갤러리 앱
- **기능**: 다음 사진/이전 사진 보기
- **구현**:
  - 각 노드가 이미지 파일 경로를 저장
  - 이중 연결 리스트로 좌우 스와이프 구현
  - 모든 이미지를 메모리에 로드하지 않고 필요할 때만 로드
- **사용 시점**: 순차적으로 탐색하는 미디어 뷰어

### 텍스트 에디터 - 커서 이동 및 텍스트 관리
**앱 예시**: VS Code, Sublime Text, Vim
- **기능**: 문자 삽입/삭제, 커서 이동
- **구현**:
  - 각 노드가 문자 또는 텍스트 블록을 나타냄
  - 중간에 문자를 삽입/삭제할 때 배열보다 효율적
  - Gap Buffer와 함께 사용하여 성능 최적화
- **사용 시점**: 대용량 텍스트 편집, 빈번한 삽입/삭제

### 운영체제 - 프로세스 스케줄링
**앱 예시**: Linux, Windows, macOS
- **기능**: 실행 대기 중인 프로세스/스레드 관리
- **구현**:
  - 각 노드가 프로세스 제어 블록(PCB)을 나타냄
  - 원형 연결 리스트로 Round-Robin 스케줄링 구현
  - 프로세스 추가/제거가 빈번하게 발생
- **사용 시점**: 작업 큐, 스케줄러 구현

### 블록체인 - 블록 체인 구조
**앱 예시**: Bitcoin, Ethereum
- **기능**: 트랜잭션 블록을 체인 형태로 연결
- **구현**:
  - 각 노드(블록)가 이전 블록의 해시값을 포함
  - 단일 연결 리스트 형태
  - 한번 추가된 블록은 변경 불가능 (Immutable)
- **사용 시점**: 블록체인, 변경 이력 추적

### 게임 - 뱀 게임 (Snake Game)
**앱 예시**: 클래식 뱀 게임, Slither.io
- **기능**: 뱀의 몸통 관리, 이동, 성장
- **구현**:
  - 각 노드가 뱀의 한 칸을 나타냄
  - 머리 방향으로 새 노드 추가, 꼬리에서 노드 제거
  - 먹이를 먹으면 꼬리 노드를 제거하지 않고 유지하여 성장
- **사용 시점**: 동적으로 길이가 변하는 객체 관리

### 메모리 관리 - Free List
**앱 예시**: 메모리 할당자, Garbage Collector
- **기능**: 사용 가능한 메모리 블록 관리
- **구현**:
  - 각 노드가 사용 가능한 메모리 블록을 나타냄
  - 메모리 할당 시 적절한 크기의 블록을 찾아 제거
  - 메모리 해제 시 Free List에 블록 추가
- **사용 시점**: 동적 메모리 할당, 메모리 풀

### 소셜 미디어 - 피드/타임라인
**앱 예시**: Facebook, Twitter, Instagram
- **기능**: 무한 스크롤, 새 게시물 추가
- **구현**:
  - 각 노드가 게시물을 나타냄
  - 연결 리스트로 시간 순서대로 정렬
  - 새 게시물은 맨 앞에 추가
  - 무한 스크롤 시 다음 노드만 로드
- **사용 시점**: 시간 순 데이터 스트림, 무한 스크롤

### 해시 테이블 - 충돌 해결 (Chaining)
**앱 예시**: Dictionary, HashMap 구현
- **기능**: 해시 충돌 시 같은 버킷에 여러 값 저장
- **구현**:
  - 각 해시 버킷이 연결 리스트의 head를 가리킴
  - 충돌 발생 시 해당 버킷의 연결 리스트에 노드 추가
  - 탐색 시 연결 리스트를 순회하며 키 비교
- **사용 시점**: 해시 테이블 구현, 충돌 해결

## 문제 풀어보기

백준 온라인 저지에서 연결 리스트 관련 문제를 난이도별로 정리했습니다. 순서대로 풀어보며 실력을 향상시킬 수 있습니다.

### 입문 단계

**[1406번 - 에디터](https://www.acmicpc.net/problem/1406)**
- 스택 또는 연결 리스트를 사용한 커서 구현
- 학습 목표: 연결 리스트의 삽입/삭제 연산 이해

**[5397번 - 키로거](https://www.acmicpc.net/problem/5397)**
- 연결 리스트를 이용한 커서 이동 및 문자 입력
- 학습 목표: 양방향 이동과 삽입/삭제

**[1158번 - 요세푸스 문제](https://www.acmicpc.net/problem/1158)**
- 원형 연결 리스트를 사용한 문제
- 학습 목표: 원형 연결 리스트의 개념

### 초급 단계

**[1168번 - 요세푸스 문제 2](https://www.acmicpc.net/problem/1168)**
- 요세푸스 문제의 최적화 버전 (세그먼트 트리 권장)
- 학습 목표: 연결 리스트의 한계와 다른 자료구조와의 비교

**[23309번 - 철도 공사](https://www.acmicpc.net/problem/23309)**
- 이중 연결 리스트를 직접 구현하는 문제
- 학습 목표: 이중 연결 리스트의 삽입/삭제 구현

**[2346번 - 풍선 터뜨리기](https://www.acmicpc.net/problem/2346)**
- 원형 연결 리스트를 활용한 시뮬레이션
- 학습 목표: 원형 연결 리스트에서의 이동

### 초중급 단계

**[1021번 - 회전하는 큐](https://www.acmicpc.net/problem/1021)**
- 양방향 순환 큐를 연결 리스트로 구현
- 학습 목표: 복잡한 연결 리스트 연산

**[3190번 - 뱀](https://www.acmicpc.net/problem/3190)**
- 뱀 게임을 연결 리스트로 구현
- 학습 목표: 연결 리스트를 활용한 시뮬레이션

**[2840번 - 행운의 바퀴](https://www.acmicpc.net/problem/2840)**
- 원형 연결 리스트를 이용한 시뮬레이션
- 학습 목표: 원형 구조의 활용

### 중급 단계

**[17255번 - N으로 만들기](https://www.acmicpc.net/problem/17255)**
- 연결 리스트의 생성 과정을 역추적
- 학습 목표: 연결 리스트 응용

**[2119번 - 선물 포장](https://www.acmicpc.net/problem/2119)**
- 복잡한 연결 리스트 조작
- 학습 목표: 고급 연결 리스트 활용

### 권장 학습 순서
1406 → 5397 → 1158 → 2346 → 23309 → 1021 → 3190 → 1168

## 배열 vs 연결 리스트

| 특성 | 배열 | 연결 리스트 |
|------|------|-------------|
| 메모리 할당 | 연속적 | 비연속적 |
| 크기 | 고정 (동적 배열은 가변) | 가변 |
| 접근 시간 | O(1) | O(n) |
| 삽입/삭제 (맨 앞) | O(n) | O(1) |
| 삽입/삭제 (중간) | O(n) | O(1) (위치를 알 때) |
| 메모리 오버헤드 | 낮음 | 높음 (포인터 저장) |
| 캐시 효율성 | 높음 | 낮음 |

## 구현 예시 (JavaScript)

```javascript
// 노드 클래스
class Node {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
}

// 단일 연결 리스트 클래스
class LinkedList {
    constructor() {
        this.head = null;
        this.size = 0;
    }

    // 맨 앞에 삽입
    insertFirst(data) {
        const newNode = new Node(data);
        newNode.next = this.head;
        this.head = newNode;
        this.size++;
    }

    // 맨 끝에 삽입
    insertLast(data) {
        const newNode = new Node(data);

        if (!this.head) {
            this.head = newNode;
        } else {
            let current = this.head;
            while (current.next) {
                current = current.next;
            }
            current.next = newNode;
        }
        this.size++;
    }

    // 특정 인덱스에 삽입
    insertAt(data, index) {
        if (index < 0 || index > this.size) {
            return false;
        }

        if (index === 0) {
            this.insertFirst(data);
            return true;
        }

        const newNode = new Node(data);
        let current = this.head;
        let previous;
        let count = 0;

        while (count < index) {
            previous = current;
            current = current.next;
            count++;
        }

        newNode.next = current;
        previous.next = newNode;
        this.size++;
        return true;
    }

    // 특정 인덱스의 데이터 가져오기
    getAt(index) {
        if (index < 0 || index >= this.size) {
            return null;
        }

        let current = this.head;
        let count = 0;

        while (count < index) {
            current = current.next;
            count++;
        }

        return current.data;
    }

    // 특정 인덱스의 노드 삭제
    removeAt(index) {
        if (index < 0 || index >= this.size) {
            return null;
        }

        let current = this.head;

        if (index === 0) {
            this.head = current.next;
        } else {
            let previous;
            let count = 0;

            while (count < index) {
                previous = current;
                current = current.next;
                count++;
            }

            previous.next = current.next;
        }

        this.size--;
        return current.data;
    }

    // 리스트 출력
    printList() {
        let current = this.head;
        let str = '';

        while (current) {
            str += current.data + ' -> ';
            current = current.next;
        }

        console.log(str + 'null');
    }
}

// 사용 예시
const list = new LinkedList();
list.insertFirst(100);
list.insertFirst(200);
list.insertLast(300);
list.insertAt(250, 2);
list.printList(); // 200 -> 100 -> 250 -> 300 -> null
```
