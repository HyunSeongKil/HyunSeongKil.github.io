---
layout: single
title: "[Tech - c#]Thread.Sleep vs Task.Delay"
# categories:[misc]
# tags:[기타]
---

# c#에서의 Thread.Sleep vs Task.Delay

| 구분              | Thread.Sleep                                                                                                | Task.Delay                                                                                                                                             |
| ----------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 같은점            | 지정한 시간동안 지연                                                                                        | 지정한 시간동안 지연                                                                                                                                   |
| 동기/비동기       | 동기                                                                                                        | 비동기                                                                                                                                                 |
| Thread 차단       | 예                                                                                                          | 아니요                                                                                                                                                 |
| 구현 난이도       | 낮음                                                                                                        | 높음                                                                                                                                                   |
| blocking          | 예                                                                                                          | 아니요                                                                                                                                                 |
| 어플리케이션 성능 | 느림(쓰레드 중지에 의한 성능저하 우려)                                                                      | 빠름                                                                                                                                                   |
| MSDN              | [Sleep](https://learn.microsoft.com/ko-kr/dotnet/api/system.threading.thread.sleep?view=net-8.0#definition) | [Delay](<https://learn.microsoft.com/ko-kr/dotnet/api/system.threading.tasks.task.delay?view=net-8.0#system-threading-tasks-task-delay(system-int32)>) |

## 동기(sync) vs 비동기(async)

| 구분 | 동기(sync)                                                        | 비동기(async)                                  |
| ---- | ----------------------------------------------------------------- | ---------------------------------------------- |
| 특징 | 선행작업이 완료될 때 까지 다음 작업 실행할 수 없음(실행되지 않음) | 선행작업과 관계없이 다른 작업 동시에 실행 가능 |
