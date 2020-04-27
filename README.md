# jacoco-diff
在 jacoco 覆盖率报告的基础上，计算出增量覆盖率


# 结果展示
### 命令行提示
![pic](https://github.com/raoweijian/jacoco-diff/blob/master/pics/help.png)

### 覆盖率报告

新增的行首增加蓝色钻石标志，与其它钻石不冲突

![pic](https://github.com/raoweijian/jacoco-diff/blob/master/pics/report.png)

# 用法
```shell
# 假设工程路径为 ~/project/test_project
cd ~/project/test_project

# 执行单测，生成 jacoco 覆盖率报告
mvn clean test

# 使用本工具，计算增量覆盖率，并修改覆盖率报告
python main.py -d ~/project/test_project -o HEAD~1
```

## 参数说明
  \-h, \-\-help        打印帮助信息
  
  \-d, \-dir           工程根目录
  
  \-o, \-old_version   指定对比的版本号, 如果该参数没有给出，默认与前一个版本进行对比(HEAD\~1)。该参数支持 git commit hash 或者 HEAD~n 的格式。
