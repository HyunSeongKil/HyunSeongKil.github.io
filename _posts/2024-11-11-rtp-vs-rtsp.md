---
layout: single
title: "[Tech - 멀티미디어]RTP vs RTSP 
# categories:[misc]
# tags:[기타]
---

# RTP vs RTSP

| 구분 | RTP                             | RTSP                                              |
| ---- | ------------------------------- | ------------------------------------------------- |
| 정의 | 멀티미디어 데이터 전송 프로토콜 | 인터넷에서 스트리밍을 제어하는 위한 표준 프로토콜 |
| 기능 | 멀티미디어 데이터 전송          | 제어(play, stop, pause,...)                       |

## RTP(Realtime Transport Protocol)

RTSP를 통해 제어되는 미디어 데이터를 실제로 전송하는 프로토콜이다.

## RTSP(Realtime Streaming Protocol)

IETF(Internet Engineering Task Force)가 개발한 프로토콜로, 스트리밍 데이터를 제어한다.
오디오, 비디오등 멀티미디어 데이터를 포함하는 미디어 서버를 원격 조작하기 위한 프로토콜
HTTP를 통해 직접 스트리밍 할 수 없습니다.

- 정의
- 특징
- 요소기술
- 주요 메소드
- RTCP(Realtime Control Protocol)

## 부록(Appendix)

### RTMP(Realtime Messaging Protocol)

어도비 시스템즈사의 독점 컴퓨터 프로토콜(이전 macromedia의 것을 인수)
오디오/비디오, 기타 데이터등 인터넷을 통해 스트리밍할 때 사용
HTTP 연결을 통해 RTMP 피드를 직접 스트리밍할 수 없습니다.
Flash Media Server와 같은 특수 서버에 연결하고 타사 CDN을 사용해야 합니다.

### HLS(HTTP Live Streaming)

애플에 의해 2009년 제안된 라이브 스트리밍 프로토콜입니다.
일반 웹서버에서도 라이브 스트리밍이 가능합니다.
하나의 영상을 10초 단위로 쪼개어 재생 목록을 만든 후 다운로드해서 재생하는 방식으로, 기존의 웹서버를 그대로 사용할 수 있습니다.

---

tcp/udp
실시간 스트리밍

https://blog.naver.com/PostView.nhn?blogId=osw9987&logNo=130131033548
https://ccusean.tistory.com/entry/RTSP-%EA%B8%B0%EC%B4%88-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-%EC%89%BD%EA%B2%8C-%EC%84%A4%EB%AA%85%ED%95%9C-%EC%8B%A4%EC%8B%9C%EA%B0%84-%EC%8A%A4%ED%8A%B8%EB%A6%AC%EB%B0%8D-%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C
https://m.blog.naver.com/dreamxpeed/222798210229
https://jee00609.github.io/live%20stream/Live-Stream/
