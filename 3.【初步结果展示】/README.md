### 数据展示（服装搭配组合图像展示）
#### 一、前期准备
* 图像归类处理完成， _/root/cai/pics_classfied/_ 完成对所有服装图像的分类和归类

* 读取的文件
|文件名称|文件说明|备注|
|---|---|---|
|pics_classfied/*|编号为 * 的服装图像数据集合|同一类的服装图像数据|
|dim_items.txt|item_id和cat_id的对应关系表|用于确定item_id对应图片所在的位置|
|dim_fashion_matchsets.txt|专家推荐的服装搭配集合|包含服装搭配组合信息|

* 输出的文件
|图像信息|数据说明|备注|
|---|---|---|
|pics_matches/matchsets|服装搭配组合信息|服装组合，其中可替代的服装的在同一列展示|

#### 二、基本思路
* 读取dim_fashion_matchsets.txt表，获取搭配组合集合；
* 读取dim_items.txt表，确定item_id对应的图片路径；
* 遍历组合，拼接图片，实现搭配组合的可视化

#### 三、实现过程
* 详见index_img.ipynb

#### 四、结果
* 详见pics_matches/matchsets/*.png
* 存在搭配组合失败的情况，需要排查
