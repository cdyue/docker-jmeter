### Usage

```
version: '2'
services:
  jmeter:
    image: libac/docker-jmeter:4.0
    command: "-n -t /jmeter/API_Regression_Testing.jmx -Jcsv /jmeter/API_Regression_ServerList.csv -Jcsv /jmeter/skip_testcase.csv -l /results/result.jtl"
    volumes:
      - ./src/:/jmeter/
      - ./src/log/:/results/
    network_mode: "bridge"
    container_name: jmeter
    environment:
      - TZ=Asia/Shanghai
```
