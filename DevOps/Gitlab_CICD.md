![Screen Shot 2022-01-03 at 3.44.56 PM](https://gitee.com/sirius_wang_wf/typora/raw/master/images/Screen%20Shot%202022-01-03%20at%203.44.56%20PM.png)

![Screen Shot 2022-01-03 at 3.49.52 PM](https://gitee.com/sirius_wang_wf/typora/raw/master/images/Screen%20Shot%202022-01-03%20at%203.49.52%20PM.png)

![Screen Shot 2022-01-03 at 3.55.22 PM](https://gitee.com/sirius_wang_wf/typora/raw/master/images/Screen%20Shot%202022-01-03%20at%203.55.22%20PM.png)

![Screen Shot 2022-01-03 at 3.56.00 PM](https://gitee.com/sirius_wang_wf/typora/raw/master/images/Screen%20Shot%202022-01-03%20at%203.56.00%20PM.png)

![Screen Shot 2022-01-03 at 3.56.57 PM](https://gitee.com/sirius_wang_wf/typora/raw/master/images/Screen%20Shot%202022-01-03%20at%203.56.57%20PM.png)

![Screen Shot 2022-01-03 at 4.32.32 PM](https://gitee.com/sirius_wang_wf/typora/raw/master/images/Screen%20Shot%202022-01-03%20at%204.32.32%20PM.png)

`tags`： 制定 runner 的tag。用于允许该项目的所有runner 列表中选择特定的Runner，在Runner注册期间，你可以指定Runner的标签

```yaml
windows job:
  stage:
    - build
  tags:
    - windows
  script:
    - echo Hello, %USERNAME%!

osx job:
  stage:
    - build
  tags:
    - osx
  script:
    - echo "Hello, $USER!"
```

`allow_failure`: 允许作业失败，默认值为`false`，启用后，如果作业失败，该作业将在用户界面显示橙色警告，但是pipeline依旧会成功，不会被阻塞

```yaml
job1:
  stage: test
  script:
    - execute_script_that_will_fail
  allow_failure: true
```

`when`:控制作业执行

- `on_success`: 前面阶段中的所有作业都成功时才执行作业，默认值
- `on_failure`: 当前面阶段出现失败时执行
- `always`: 总是执行
- `manual`: 手动执行
- `delayed`: 延迟执行

`retry`: 失败后重试的默认值 [0, 2]

- max

- when

  <img src="https://gitee.com/sirius_wang_wf/typora/raw/master/images/Screen%20Shot%202022-01-03%20at%206.32.05%20PM.png" alt="Screen Shot 2022-01-03 at 6.32.05 PM" />

`timeout`: 作业的超时，项目的超时，Runner的超时

```yaml
build:
  script: build.sh
  timeout: 1h 30m
test:
  script: rspec
  timeout: 1 hours 10 minutes
```

`paraller`: 并行作业，配置要并行运行的作业实例数，[2, 50]

```yaml
before_script:
  - echo "before script"
variables:
  DOMAIN: example.com
stages:
  - build
  - test
  - codescan
  - deploy
  
build:
  before_script:
    - echo "before script in job"
  stage: build
  script:
    - echo "mvn clean install"
    - echo "$DOMAIN"
  after_script:
    - echo "after script in build job"

unittest:
  stage: test
  script:
    - echo "run test"
  when: delayed
  start_in: "5"
  allow_failure: true
  retry:
    max: 1
    when:
      - script_failure
  timeout: 1 hours 10 minutes
  
deploy:
  stage: deploy
  script:
    - echo "hello deploy"
    - sleep: 2
  when: manual
  
codescan:
  stage: codescan
  script:
    - echo "codescan"
    - sleep: 5
  when: on_success
  parallel: 5
  
after_script:
  - echo "after script"
```

`rules`:  构建规则，允许按顺序评估单个规则，直到匹配并为作业动态提供属性

- `if `（如果条件匹配）
- `change `（指定文件发生变化）
- `exists`（指定文件存在）

