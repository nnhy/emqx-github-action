<div align="center">
  <p>
    <h3>EMQ in GitHub Actions</h3>
  </p>
  <p>启动一个EMQ，用于测试</p>
</div>

---

## 简介

使用docker容器启动一个EMQ实例，用于自动化测试。

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
        uses: nnhy/emqx-github-action
  
      - name: Test
        run: dotnet test -c Release XUnitTestClient/XUnitTestClient.csproj
```
