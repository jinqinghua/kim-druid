# Druid

## 参考
- [druid](https://github.com/alibaba/druid)
- [druid-spring-boot-starter](https://github.com/alibaba/druid/tree/8ad802e74bff7e861ca2fb02131478a3e120449c/druid-spring-boot-starter)

## 实用功能
### 数据库监控
application.yml
```yml
spring:
  datasource:
    druid:
      stat-view-servlet:
        enabled: true
        url-pattern: /druid/*
        reset-enable: false
        login-username: admin
        login-password: "9Bugaosun!"
```
### 数据库加密

```shell
java -cp druid-1.1.23.jar com.alibaba.druid.filter.config.ConfigTools your_password

privateKey:MIIBVQIBADANBgkqhkiG9w0BAQEFAASCAT8wggE7AgEAAkEAvUO2TMHDlRMv8CSpj4H5wvrBRwDcVxMtH8Z/984FK50U9n/MIWl7MCx+s6fLQT8BK7CJwDwcFc0pzW2FQKh+uQIDAQABAkEAgGbl0
OFL/WFNDpDw8Elv1xYj9jXhRrndzUbwHoCJBXKZ0Uq341UiNXop54BrsSTLBqEikNRX/LZ1bKuaqVywAQIhAPcUz23F9VPE2fCeupZ2J0d0sEwxgHJGB9I5ugwmfAu5AiEAxBijOQA1/wfxJjzBtJsX7octJNKTr
U5kZ3wcizvHiwECIFNRvTEzVCtPcn7lx939Mfmyq9DF0J64ZuLJfKekQqhhAiEAnUd1gr5ckJR6IkUQyB6s7y+UUbhjodkCRs4QxsvHnAECIBlgSHUU+cN+vyaxuzOPTO33xexWF40B7PKHIF1cN1GW
publicKey:MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAL1DtkzBw5UTL/AkqY+B+cL6wUcA3FcTLR/Gf/fOBSudFPZ/zCFpezAsfrOny0E/ASuwicA8HBXNKc1thUCofrkCAwEAAQ==
password:qEVZM1nJ6SWkWPjmItczrvvFVsb5QwpwaHunycsf6jMyHRC9Uer2vaGDvCw/UcD6KAO4r9AoOESOXhBceU60wQ==
```

application.yml
```yml
spring:
  datasource:
    password: qEVZM1nJ6SWkWPjmItczrvvFVsb5QwpwaHunycsf6jMyHRC9Uer2vaGDvCw/UcD6KAO4r9AoOESOXhBceU60wQ==
    druid:
      filters: config
      connectionProperties: "config.decrypt=true;config.decrypt.key=MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAL1DtkzBw5UTL/AkqY+B+cL6wUcA3FcTLR/Gf/fOBSudFPZ/zCFpezAsfrOny0E/ASuwicA8HBXNKc1thUCofrkCAwEAAQ=="
```
