# Xiaomi-Mobile-Sales-Data-Analysis-Project

cellphone.csv（淘宝网在售的手机商品信息）
#   Column                        Non-Null Count  Dtype  
---  ------                        --------------  -----  
 0   爬取时间(__time)                  1691 non-null   object 
 1   爬取链接(__url)                   1691 non-null   object 
 2   商品ID(product_id)              1691 non-null   int64  
 3   商品名称(name)                    1691 non-null   object 
 4   商品描述(description)             1587 non-null   object 
 5   商品参数(params)                  1691 non-null   object 
 6   商品现价(current_price)           1691 non-null   object 
 7   商品原价(original_price)          1691 non-null   object 
 8   月销量(month_sales_count)        1684 non-null   float64
 9   库存(stock)                     1675 non-null   float64
 10  发货地址(shipping_address)        1691 non-null   object 
 11  商品发布时间(product_publish_time)  1691 non-null   int64  
 12  店铺ID(shop_id)                 1691 non-null   int64  
 13  店铺名称(shop_name)               1691 non-null   object 
 14  商品链接URL(url)                  1691 non-null   object 
 15  评分（总分5.0分）(score)             1680 non-null   float64
 16  收藏数(stores_count)             1691 non-null   int64  
 17  累计评价数(comments_count)         1679 non-null   float64
 18  商品评价印象标签(impresses)           1691 non-null   object 
 19  Unnamed: 19                   0 non-null      float64

count_add_comments.csv（手机商品的评价信息）
 #   Column      Non-Null Count  Dtype  
---  ------      --------------  -----  
 0   图片(picNum)  1232 non-null   float64
 1   追评(used)    1176 non-null   float64
 2   ID(id)      1691 non-null   int64  
 3   Unnamed: 3  0 non-null      float64

comments.csv（手机商品的具体评价）
 #   Column         Non-Null Count   Dtype  
---  ------         --------------   -----  
 0   商品ID(id)       376760 non-null  int64  
 1   评价时间(time)     376760 non-null  object 
 2   评价内容(content)  376759 non-null  object 
 3   爬取链接(spurl)    376760 non-null  object 
 4   爬取时间(sptime)   376760 non-null  object 
 5   Unnamed: 5     0 non-null       float64


 从数据类型中分析
 # 手机品牌统计_词云
 # 手机价格区间统计_直方图
 # TOP10品牌 手机价格等级构成_堆积柱形图
 # 不同价格等级下的总销售额_饼图_从总体上研究价格与总销售额关系
 # 各个品牌下商品现价与原价对比_分组条形图
 # 各个品牌下收藏数与商品现价的关系_折线图_研究用户是否能突破品牌限制而只关心商品现价而进行收藏商品
 # 各个品牌下销量与商品现价的关系_折线图_研究用户是否能突破品牌限制而只关心商品现价而进行购买商品
# 各个品牌的总销量_条形图
# 各发货省销售情况_地图
# 不同价格等级下的总销量_饼图_从总体上研究价格与销量关系
# 不同价格等级下的总销售额_饼图_从总体上研究价格与总销售额关系

数据清洗cellphone.csv存在空白列，且商品描述、月销量、库存、评分、累计评价数存在缺失值

对add_comments和 phone 进行数据合并,并尽心初步清洗
#   Column      Non-Null Count  Dtype  
---  ------      --------------  -----  
 0   爬取时间        1691 non-null   object 
 1   爬取链接        1691 non-null   object 
 2   商品ID        1691 non-null   int64  
 3   商品名称        1691 non-null   object 
 4   商品描述        1587 non-null   object 
 5   商品参数        1691 non-null   object 
 6   商品现价        1691 non-null   object 
 7   商品原价        1691 non-null   object 
 8   月销量         1691 non-null   float64
 9   库存          1691 non-null   float64
 10  发货地址        1691 non-null   object 
 11  商品发布时间      1691 non-null   int64  
 12  店铺ID        1691 non-null   int64  
 13  店铺名称        1691 non-null   object 
 14  商品链接URL     1691 non-null   object 
 15  评分          1680 non-null   float64
 16  收藏数         1691 non-null   int64  
 17  累计评价数       1691 non-null   float64
 18  商品评价印象标签    1691 non-null   object 
 19  图片(picNum)  1232 non-null   float64
 20  追评(used)    1176 non-null   float64
 21  ID(id)      1691 non-null   int64  
 22  Unnamed: 3  0 non-null      float64
 存在空白列，且评分、图片、追评存在缺失值，商品发布时间不符合规范，使商品价格取平均值，规范为单独一个值，将发货地址整合为省级，添加一个价格等级，提取出手机参数中的有用信息，并删除爬取时间、爬取链接，新生成清洗数据后的文件。

 进行数据可视化
 处理后的数据.csv
 #   Column      Non-Null Count  Dtype  
---  ------      --------------  -----  
 0   Unnamed: 0  1691 non-null   int64  
 1   商品ID        1691 non-null   int64  
 2   商品名称        1691 non-null   object 
 3   商品描述        1587 non-null   object 
 4   商品参数        1691 non-null   object 
 5   商品现价        1691 non-null   float64
 6   商品原价        1691 non-null   float64
 7   月销量         1691 non-null   float64
 8   库存          1691 non-null   float64
 9   发货地址        1691 non-null   object 
 10  商品发布时间      1691 non-null   object 
 11  店铺ID        1691 non-null   int64  
 12  店铺名称        1691 non-null   object 
 13  商品链接URL     1691 non-null   object 
 14  评分          1680 non-null   float64
 15  收藏数         1691 non-null   int64  
 16  累计评价数       1691 non-null   float64
 17  商品评价印象标签    1691 non-null   object 
 18  图片          1232 non-null   float64
 19  追评          1176 non-null   float64
 20  发货城市        1691 non-null   object 
 21  发货省份        1691 non-null   object 
 22  价格等级        1691 non-null   object 
 23  后置摄像头       1672 non-null   object 
 24  摄像头类型       1672 non-null   object 
 25  视频显示格式      1672 non-null   object 
 26  分辨率         1672 non-null   object 
 27  触摸屏类型       1672 non-null   object 
 28  屏幕尺寸        1673 non-null   object 
 29  网络类型        1680 non-null   object 
 30  网络模式        1672 non-null   object 
 31  键盘类型        1672 non-null   object 
 32  款式          1672 non-null   object 
 33  运行内存RAM     1672 non-null   object 
 34  存储容量        1680 non-null   object 
 35  品牌          1680 non-null   object 
 36  华为型号        275 non-null    object 
 37  电池类型        1672 non-null   object 
 38  核心数         1672 non-null   object 
 39  机身颜色        1680 non-null   object 
 40  手机类型        1673 non-null   object 
 41  操作系统        1673 non-null   object 
 42  CPU品牌       1673 non-null   object 
 43  产品名称        1454 non-null   object 