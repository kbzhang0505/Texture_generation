# 多模态数据驱动的纺织印花纹理与时尚服装可控生成

近年来，我国纺织服装行业在产业规模、技术水平和全球影响力等方面取得了显著进展。然而，在智能化转型与高质量发展过程中，仍面临创新能力不足、设计成本高且效率低、产品技术含量不高以及绿色环保技术相对滞后等突出问题。依托西安工程大学纺织科学与工程特色学科优势，本课题以纺织数码印花图案的智能生成为切入点，开展了多模态印花图案布局控制、纹理边缘可控的无限平铺生成以及多模态时尚服装可控生成等关键技术研究。通过构建从面料图案生成到纹理与款式协同控制的时尚服装生成技术体系，实现了图案设计与服装生成的一体化探索，为推动我国纺织服装行业的智能化与数字化转型升级提供了重要的技术支撑。

# 数码印花图案数据集构建

目前，缺少公开可用的文本到印花图案生成研究的高质量数码印花图案基准数据集，为此本课题组自主建立了纺织数码印花纹理数据集TileVL。该数据集包括3 090对文本描述和无水印数码印花图案样本对，每张图案分辨率为512像素×512像素。图案数据主要来源于各种纺织数码印花素材平台。该数据集包含抽象、水彩、卡通、田园、现代艺术和中国风等12种图案风格。图案布局包括斜向排列、交错排列和方阵排列等。文本标注按照无缝、风格、对象色彩、对象名称、排列布局、背景色彩的顺序进行英文描述。这种描述形式有助于模型更全面的学习图案风格、色彩、对象、排列布局和背景色彩等特征。该数据集部分样本如下图所示：

<img width="1280" height="946" alt="粉红牡丹花设计素材集" src="https://github.com/user-attachments/assets/7b5ca08b-e2ac-4651-bdb6-bc25d88bd77e" />

# 纺织数码印花图案布局可控生成研究成果

目前，纹理布局控制方法主要存在布局控制准确性差和色彩属性绑定错误的问题：

<img width="1246" height="713" alt="花卉纹理设计-错误分析" src="https://github.com/user-attachments/assets/26690703-6a1c-451f-80b3-7d9e1ec17b96" />

本课题组基于构建的TileVL印花数据集提出多文本要素联合的交叉注意力激励图案布局控制方法DippDiff。布局控制和色彩生成准确性显著提升，可视化效果如下：

<img width="1112" height="946" alt="粉花叶纹样设计-无缝风格" src="https://github.com/user-attachments/assets/c6445017-5552-4a6b-b904-3cb489da7c14" />

# 纺织数码印花图案四方连续生成研究

现有纹理平铺方法在处理复杂印花图案的边缘平铺性任务时存在边缘接缝伪影的问题，为此本课题组提出了一种名为BiSeDiff的扩散生成框架，实现将非平铺示例图案转化为可平铺图案。通过在去噪过程中交替进行双向特征平移与标准去噪，使图像边界信息被移动到中心区域进行修复，从而生成无缝连续的纹理图案。与此同时，结合纹理对齐模块和重叠解码方法，在保持示例纹理结构与风格一致性的同时，实现高质量、无边界接缝的大尺寸纹理生成。该方法主要研究成果如下：

<img width="1219" height="806" alt="印花图案四方连续图" src="https://github.com/user-attachments/assets/a718e28e-3e13-41a4-9ec5-3a526cc48631" />

4x4平铺效果展示：
<img width="1474" height="1513" alt="More_visualize_result_4x4-新" src="https://github.com/user-attachments/assets/131483be-3123-4f84-b79e-1a415ccc5ef7" />

8x8平铺效果展示：
<img width="2000" height="2270" alt="More_visualize_result_8x8_a" src="https://github.com/user-attachments/assets/dba6ddd2-badb-4aba-bc67-e05e9498c563" />
<img width="2000" height="2269" alt="More_visualize_result_8x8_d" src="https://github.com/user-attachments/assets/c0791b40-9af4-4354-88fb-ec84b471f240" />

文本到边缘无限平铺图案生成效果：

![t2i_result-2](https://github.com/user-attachments/assets/dcbb933e-3061-4d7b-832f-d0b201b46cae)
![t2i_result0-1](https://github.com/user-attachments/assets/48dbf073-a818-4b35-bb2c-b6219470345e)

# 时尚服装可控生成

# 多模态服装数据集
多模态服装图像生成技术的发展受到现有数据集中图像分辨率低和标注稀疏的限制。为了缩小这一差距，我们扩展了高分辨率的Dress Code和VITON-HD数据集，通过添加对齐的多模态标注（包括文本描述、线条图和面料纹理）来丰富其店铺内服装图像，分别构建了Dress Code Garment和VITON-HD Garment数据集。该数据集样本示例如下（除了原始的店内服装图像，我们还提供了文本描述、纹理图和线稿图）:

<img width="6614" height="1583" alt="微信图片_20260310175845_1075_53" src="https://github.com/user-attachments/assets/7654e8ca-6088-4ee8-bf88-73ab553aec69" />

我们利用构建的数据集进行了多模态服装图像生成实验，并取得了令人满意的结果。该数据集支持多种条件模态的融合，从而实现可控且精细的服装生成。实验结果表明，该数据集能够为多模态服装生成模型提供有效的监督，并有助于生成高质量的服装图像。部分实验结果如下：

<img width="6131" height="2872" alt="微信图片_20260310175846_1076_53" src="https://github.com/user-attachments/assets/c1ccb4e3-1b8a-496c-9eec-1ce63d56c05c" />
