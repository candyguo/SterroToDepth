*  SGM
hand on hand explanation about SGM (respect it)
https://ethanli.blog.csdn.net/article/details/105715526

通过局部方法先形成初始代价空间，再利用全局信息（4 path or 8 path）形成聚合代价空间, 然后再进行视差
计算与视差优化

视差优化部分包括的子模块：
1. 子像素拟合
2. 左右一致性检查
3. 唯一性约束
4. 小连通区域剔除
5. 中值滤波
6. 弱纹理区优化
7. 空洞填补（视差填充）
视差优化的目的：提高视差精度,剔除错误视差,使得视差值精确,可靠

2-4均是为了剔除掉错误视差，同时要保持左右一致性和唯一性
加入视差图的中值滤波可以去掉视差噪声,采用双边滤波也可以,可以同时保持边缘的精度,但效率稍低

* 按照实际的需求来确定是否需要进行视差填充, 如果要求每个像素都尽量精确, 而不要求完整,那就不需要做视差
填充,如果要求视差图完整,而对精确性要求不高,那就需要做视差填充