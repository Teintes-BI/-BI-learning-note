公司的Rna-seq流程

​	tophat2 -> cufflinks -> cuffdiff -> R

富集分析：

​	GO

​	KEGG

​	DO（经常不做）

用的已经成熟的Database ，容易过时



####  Gene Ontology 基因本体论
- cellular component CC 在细胞的哪个部位
- biological process BP 生物过程
- molecular function MF 分子功能

以上三个维度的描述代表了对基因的注释信息（annotation）。

RNA-seq 
- ctrl 在一种条件下的基因表达distribution
- treatment 另一种？

crtl vs treatment - >DEG
DEG: differential expression genes 差异表达基因

tophat 是把reads 贴到基因组上。
cufflinks 计算基因表达量
cuffdiff 比较Ctrl和treatment  找出DEG

DEG -> GO annotation
期待：找出能在GO三维度找出和背景不一样的内容

所以要做GO分析

model organism -> annotated db
non-model organism ->  search db (blast)

 
