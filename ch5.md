# 5장 안정 해시 설계

수평적 규모 확장성을 달성하기 위해서는 요청 또는 데이터를 서버에 균등하게 나누는게 중요하다.

<br />

## 해시 키 재배치(rehash) 문제

N개의 캐시 서버들에 부하를 균등하게 나누는 보편적인 방법은 아래와 같다

```js
serverIndex = hash(key) % N; // N은 서버 대수
```

이 방식은 서버 풀(pool) 이 고정되어 있을떄는 유효하지만 1번 서버가 장애를 일으켜 죽으면 서버 풀의 크기가 변하므로

나머지 연산의 결과가 달라져 캐시미스가 발생할수도 있다.

이 뒤부터 이해가 안됩니다 ..

<br />

## 안정 해시

##
