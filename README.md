<div align="center">
  <p>
    <h3>EMQ in GitHub Actions</h3>
  </p>
  <p>启动一个EMQ，用于MQTT测试</p>
</div>

---

## 简介

使用docker容器启动一个EMQ实例，用于MQTT自动化测试。

## 用法

```yaml
name: test

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Git checkout
        uses: actions/checkout@v2
  
      - name: Setup EMQ
        uses: nnhy/emqx-github-action@v1.0
  
      - name: Test
        run: dotnet test -c Release XUnitTestClient/XUnitTestClient.csproj
```
