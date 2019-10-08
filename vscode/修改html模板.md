# 修改html模板
点开：file>preferences>User snippets
输入html选择html.json就可以修改了
添加下面内容
```json
"h5 sample": {
    "prefix": "!",
    "body": [
      "<!DOCTYPE html>",
      "<html lang=\"zh-CN\">\n",
      "<head>",
      "\t<meta charset=\"UTF-8\">",
      "\t<meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0,minimal-ui:ios\">",
      "\t<meta http-equiv=\"X-UA-Compatible\" content=\"ie=edge\">",
      "\t<title>Document</title>",
      "\t<link rel=\"stylesheet\" href=\"$1\">",
      "\t<script src=\"$2\"></script>",
      "</head>\n",
      "<body>\n$3",
      "</body>\n",
      "</html>"
    ],
    "description": "The full sample code - html5."
  }
```
$1 $2 表示光标的位置，按tab键跳转,$0是最后一个
[借鉴网页](https://blog.csdn.net/yohoj/article/details/84099534)
> 这里的 “prefix”: “!”,指的是你自定义的快捷代码，这里我输入h就会出现快速生成代码提示，也可以自定义其他字段。
