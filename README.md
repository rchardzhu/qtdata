# qdata
量化数据源众多，参考https://github.com/rchardzhu/awesome-quant-cn

金融数据是量化的基础，没有数据量化就无从下手。随着行业竞争加剧，量化对高质量—更快更全更准数据的要求更高，毕竟搞量化不能输在起跑线上。现在各种量化数据源五花八门，发现很多朋友对这块不是很清楚，个人也在上面花了不少时间，希望能跟大家一起共建，感兴趣的朋友可以关注公众号加群一起交流。 微信公众号：诸葛说talk

各种数据源格式各不相同，本代码库希望能够把各种数据源统一起来，大家只需要依赖这个lib库就好。
本代码库预计实现的功能：
* 适配各类数据源，对量化感兴趣的同学只使用一套代码库就可以使用各种数据
* 输出为pandas格式，方便直接使用
* 可以存储到本地行情库，也可以从本地行情库读取


量化数据源分为如下几种： 开源量化数据、券商/量化交易平台提供的数据源、专业数据服务公司和自己抓取清洗几种方式。
### 开源量化数据

通过抓取各类财经网站或公开的金融数据，进行清洗加工存储后开放出来，为量化学习者提供金融数据需求

- [BaoStock](http://baostock.com) -- 一个免费、开源的证券数据平台（无需注册），通过python API获取证券数据信息，返回的数据格式为pandas DataFrame类型，同时支持通过BaoStock的数据存储功能，将数据全部保存到本地后进行分析。 优点是免费，缺点是数据不全
- [tushare](https://waditu.com/document/1?doc_id=131) -- 分为tushare和tushare pro。tushare pro数据覆盖范围广，但获取次数较多时有积分限制，。老版api只提供基础日线数据。 tushare pro现金积分充值比例是1:10，比如充值200获取2000积分，积分有效期一年， 使用数据积分不减少。[A股2000积分可以使用，但限频次，每分钟限200次请求，每天限10w次api请求。](https://tushare.pro/document/1?doc_id=290) 港美股日线需至少5000积分。 分钟级数据需要单独开权限的，跟平台积分没有关系，需要单独申请。
- [akshare](https://github.com/akfamily/akshare) -- 基于 Python 的财经数据接口库, 目的是实现对股票、期货、期权、基金、外汇、债券、指数、加密货币等金融产品的基本面数据、实时和历史行情数据、衍生数据从数据采集、数据清洗到数据落地的一套工具。akshare api接口变动较频繁，数据格式不通用
- [yfinace](https://github.com/ranaroussi/yfinance) -- yahoo财经数据获取，需要使用代理访问
- [easyquotation](https://github.com/shidenggui/easyquotation)-- python实时获取新浪/腾讯的全市场行情，无法获取历史数据
- [efinance](https://github.com/Micro-sheep/efinance) -- 用于获取股票、基金、期货、债券数据的免费开源 Python 库

### 券商/量化交易平台

- [聚宽数据JQData](https://www.joinquant.com/data) -- 聚宽提供了本地量化金融数据服务[jqdatasdk](https://www.joinquant.com/help/api/help#name:JQData) 。申请可以获得三个月的试用期，一个手机号仅限注册一次。[申请链接](https://www.joinquant.com/default/index/sdk?utm_campaign=JQData%E7%94%B3%E8%AF%B7&utm_medium=%E7%BD%91%E9%A1%B5&utm_source=%E8%81%9A%E5%AE%BD&gio_link_id=xRxqAjP5)
- [rqdata](https://www.ricequant.com/welcome/pricing)-- 米筐提供的数据服务。免费试用15天，试用账户每天 50MB 的配额限制，[申请链接](https://www.ricequant.com/welcome/purchase#1)
- [tqsdk](https://doc.shinnytech.com/tqsdk/latest/intro.html) -- TqSdk免费版本提供全部的期货、商品/金融期权和上证50、沪深300和中证500的实时行情，TqSdk专业版可提供A股股票的实时和历史行情
- [futu openapi](https://openapi.futunn.com/futu-api-doc/): 富途提供的量化api，可以获取历史行情和实时行情，根据账号金额等级对应不同的数据获取权限

### 专业数据服务公司

- [万得Wind Data Service数据服务](https://www.wind.com.cn/NewSite/data.html) **—** 约3~6w人民币/年，具体需要咨询销售，国内金融数据万得相对更全
- [ifind](https://www.51ifind.com/index.php?c=index&a=iFinDPC) — 同花顺金融数据终端，定价约wind的1/3
- [choice数据](https://choice.eastmoney.com/) — 东方财富数据终端，choice质量据说不如ifind
- [彭博bloomberg数据服务](https://www.bloombergchina.com/solution/data-content/) — 约2w刀/年，具体需要咨询销售

### 自己抓取&清洗数据

编程能力好且有时间的朋友，也可以自己抓取和清洗数据。好处是数据质量有保障，可以按照自己要求来进行处理；缺点是对编程能力有一定要求，且比较费时间人力。

比较常见的是对特定数据当上面的数据源无法覆盖时，可以自己抓取补充。



