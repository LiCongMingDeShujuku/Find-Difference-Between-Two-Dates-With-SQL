![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 找出两个日期之间的差异
#### Find Difference Between Two Dates With SQL
**发布-日期: 2015年09月28日 (评论)**

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
你有没有找到大多数人都能理解的查找两个日期之间的差异的方法？下面这些快速的逻辑（logic），能帮你找到两个日期间的差异。

## English
Ever find yourself needing to find the difference between two dates, but displaying in such a way that makes sense to most people? Here’s some quick sql logic to get you the difference.

---
## Logic
```SQL
declare @last_date datetime = '2015-09-26 14:00:01.670'
 
select case
when datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 / 12 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 / 12 as nvarchar(50)) + ' Yr ' end +
case
when datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 % 12 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 % 12 as nvarchar(50)) + ' Mo ' end +
case
when datediff(second, @last_date, getdate()) / 60 / 60 / 24 % 30 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 / 24 % 30 as nvarchar(50)) + ' Dy ' end +
case
when datediff(second, @last_date, getdate()) / 60 / 60 % 24 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 % 24 as nvarchar(50)) + ' Hr ' end +
case
when datediff(second, @last_date, getdate()) / 60 % 60 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 % 60 as nvarchar(50)) + ' mn ' end


```

[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

