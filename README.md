# bootstrap-gpt

引导 gpt 帮你高效完成各种事情, 写 gpt 程序，gpt 自动化

> pip install openai && pip install beautifulsoup4

## download

## set api key

.env

```
api_key=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## run

```
cd bootstrap-gpt
python3 ./main.py
```

## bootstrap simple

```
{
    "author": "ruidong",
    "date": "2023-04-17",
    "version": "0.1",
    "description": "帮你写代码 引导助手",
    "boot": [{
            "o": "你好 这是一个code模板 请选择模板 1.simple 2.demo",
            "b": {
                "1": 1,
                "2": 2
            }
        },
        {
            "o": "请输入语言类型",
            "b": [2]
        },
        {
            "o": "请输入需求",
            "t": "chat:写一个{{r2}}的{{r1}}程序"
        }
    ]
}
```

o: output 支持模板
b: branch 分支 支持 Object 字段 eq 跳转 和 Array 循序执行
t: template 模板 用于引导[chat:] chatgpt 给其文案 或 爬虫[sprider:] 纯文本[text:]

r2 r1 为变量名称 为类型+index 索引 有 r：reader p:prompts m:msg 之分
生成规则参考[interpreter.py](./interpreter.py)
