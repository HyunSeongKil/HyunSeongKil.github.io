## transient vs scoped vs singleton

- **transient** : Transient objects are always different; a new instance is provided to every controller and every service.
- **scoped** : Scoped objects are the same within a request, but different across different requests.
- **singleton** : Singleton objects are the same for every object and every request.

## App.config

- 개발할 때 App.config 파일로 핸들링
- 빌드 후 실행파일명.config 파일로 변환됨
  - 예) 실행파일명: Program.dll => Program.dll.config

```
// 1/4 App.config 파일 편집
<configuration>
...전략
  <appSettings>
    <add key="myKey" value="myValue" />
  <appSettings>
...후략
</configuration>
```

```
// 2/4 System.Configuration 참고 추가
```

```
// 3/4
using Sytem.Configuration;
```

```
// 4/4
Console.WriteLine(Configuration.AppSettings["myKey"].ToString()); // output: myValue
```
