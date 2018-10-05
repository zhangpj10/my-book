## 自述和介绍

  书本的第一页内容是从文件README.md中提取的。如果这个文件名没有出现在SUMMARY中，那么它会被添加为章节的第一个条目

## 使用其他文件替代README.md

  可在book.json中定义某个文件作为README。
  ```
	{
		"structure": {
			"readme": "myIntro.md"
		}
	}
  ```
  
## 章节和子章节
  
  使用文件SUMMARY.md来定义鼠标的章节和子章节结构，SUMMARY.md是用来生成书本内容的预览表。
  
  ### 简单例子
  ```
   [章节 1](chapter1.md)
   [章节 2](chapter2.md)
  ```
  ### 包含子章节的例子
  ```
  [卷一](part1/README.md)
	[gitbook](part1/gitbook.md)
  [卷二](part2/README.md)
	[工具](part2/tool.md)
  ```
  ### 相关插件文档连接地址
  > http://gitbook.zhangjikai.com
  