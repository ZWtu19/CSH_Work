### 数据索引（以图找图）
#### 一、前期准备
* 图像数据下载完成，下载链接可自行百度’阿里天池服装搭配xx‘
* 读取的文件
|文件名称|文件说明|备注|
|---|---|---|
|dim_items.txt|包含item_id,和对应cat_id信息|用于生成服装图像数据和分类信息的索引表|
|pics/tianchi_fm_img2_1/|包含部分服装图像信息|为服装图像的第一部分|
|pics/tianchi_fm_img2_2/|包含部分服装图像信息|为服装图像的第一部分|
|pics/tianchi_fm_img2_3/|包含部分服装图像信息|为服装图像的第一部分|
|pics/tianchi_fm_img2_4/|包含部分服装图像信息|为服装图像的第一部分|


* 输出的文件
|文件名称|文件说明|备注|
|---|---|---|
|contents.csv|存储了cat_id,和对应item_id集合信息||
|pics_classfied/cat_id|存储了cat_id信息|为文件夹，包含以cat_id命名的子文件夹|
|pics_classfied/cat_id/*.jpg|存储了item_id图像|为一系列图像，为cat_id下以item_id命名的图像合集|

#### 二、基本思路
* 本次实验只是基本的数据预处理实验，数据量较大；
* 根据'dim_items.txt'读取服装大类和服装编号的对应关系；
* 将对应类别的服装图像进行分类，具体存储在以cat_id命名的文件夹下；

#### 三、实现过程
* 定义ItemReader类，完成对文件 *dim_items.txt* 的读取；
* 定义ItemReader.aeemble():实现对读取的文件的筛选分类，得到cat_id 和item_id集合的信息；
[contents表]('res/cat_id&item_id.png')
* 将生成的contents表以表格的形式保存： *../Dataes/ResultDataes/contents.csv*；

* 定义CatFolderCreater类，完成对图片子文件夹的分类，图像的分类工作；
* 定义CatFolderCreater.creator((self,cat_id):实现对cat_id命名的系列子文件夹的生成；
* 定义CatFolderCreater.fet_imlist(self,path):实现对 _/pics/tianchi_fm_img2_*_下的服装图像编号的获取，并生成列表img2_*返回；
* 定义CatFolderCreater.pic_move(self,sets):读取contents.csv文件,根据cat_id和item_id的对应关系，将读取的列表进行遍历，依次将img2_1、img2_2、img2_3、img2_4的对应的服装图像移动到对应的cat_id/文件夹下

#### 四、结果
* 图像分类结果存储至 _/root/cai/pics_classfied/_下
* 子文件夹
[子文件夹]('res/classfied_1.png')

* 服装图像
[服装图像]('res/classfied_2.png')
