# MMDIEA(Multi-modal datasets in education area)
多模态教育数据集 包含两个数据集分别是MDKPC和MMTD

MDKPC dataset：

The dataset contains multi-modal documents data, which comes from Wikipedia. 

-->textual and graphical data of Knowledge Area（TGKD） dataset 为原始数据集
-->TGKD_train_val.npz 是处理好的数据集
-->cleandata 为筛选后的图片
-->pre_dealdata 为处理原始数据集的程序

1. 运行data 文件夹中的pre_dealdata
	读取 imagedata中相对应的 excel 文件，根据条件筛选出有效的数据，图片存入cleanimage中 并写入txt中 txt后三个字符串为 图片对应的三个标签 以" Label:“分割开
（xlrd读数据较大的excel表时效率高于openpyxl）
2. 处理好的数据 以.npz存储 包含：
	imgdetail:list形式存储 每条包含[文本描述（已word2ix）,图片地址，标签（列表表示以label2ix）]
	word2ix：文本描述中的文字映射为数字
	ix2ilabel：数字映射为文本描述中的文字
	label2ix：标签映射为数字
	ix2label：数字映射为标签
	打开方式：
	datas = np.load('./your-path/TGKD_train_val.npz',allow_pickle=True)
	imgdetail = datas['imgdetail']
	label2ix = datas['label2ix'].item()
  
MMTD dataset:
The dataset contains multi-modal documents data, which comes from Beijing Normal University. 
