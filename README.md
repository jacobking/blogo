# BLOGO (轻量级博客生成工具)

## 目录

*	[功能](#功能)
*	[下载及安装](#下载及安装)
*	[使用](#使用)
*	[命令集](#命令集)
*	[特殊标记](#特殊标记)
*	[开发数据](#开发数据)
*	[TODO](#TODO)
*	[Bugs Report](#Bugs Report)
*	[授权协议](#授权协议)

## 功能
1.  快速创建博客，并使用MarkDown写文章
2.  自定义主题(目前仅支持Jade)
3.  一条命令同步到博客目的地(目前仅支持git)
4.  拥有专门的文章demo生成工具，方便在文章中插入示例

## 下载及安装
1.  npm install blogo -g

## 使用
1.  blogo init && blogo start

## 命令集
1. blogo init (dirname) || blogo i
   
   创建博客
2. blogo new (articleName) || blogo n
   
   创建一篇新文章

   blogo new -s
   
   创建一篇新文章并且开启服务
3. blogo sample (sampleName)
   
   创建一个新示例
4. blogo start || blogo s
   
   创建一个本地web服务用来预览博客
5. blogo deploy || blogo d
   
   提交博客
6. blogo generate || blogo g
   
   手动编译md到blog
7. blogo remove (articleName) || blogo r
   
   删除一篇文章

## 特殊标记
{-demo(demoName)-}

在MarkDown中使用此标记用于在当前位置插入创建好的demo示例

## 开发数据
```
{
	"post":{
		"articles":[{
			"title":"article name",
			"date":"create time",
			"year":"create year",
			"month":"create month",
			"day":"create day",
			"time":"create time without date info",
			"desc":"article description",
			"html":"article detail html"
		},...],
		"tags":{
			"tagName":["articles" like post.articles]
		},
		"time":{
			"year":{
				"list":["articles" like post.articles],
				"month":{
					"list":["articles" like post.articles],
					"day":{
						"list":["articles" like post.articles],
						"articlesName":post.articles
					}
				}
			}
		}
		//article数据仅存在于article页面
		"article":{
			"title":"article name",
			"date":"create time",
			"year":"create year",
			"month":"create month",
			"day":"create day",
			"time":"create time without date info",
			"desc":"article description",
			"html":"article detail html"
		}
	},
	"config":{
		"resourceUrl":"your blog url + /resource"
		"social":{
			"twitter":"",
			"github":"",
			...
		},
		"email":"xx@xx.xx",
		"author":"xx",
		"blogName":"blog title",
		"disqusName":"xx"
	}
}
```

## Bugs Report
https://github.com/kevin14/blogo/issues

## TODO
1. 增加对于其他模版引擎的支持
2. 增加其他repo的支持

## 授权协议
Released under the MIT, BSD, and GPL Licenses