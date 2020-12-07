outfmt -6输出的调整记录

首先，按您标记的内容敲代码，出现报错

	 blastp -query LGQ26100+.fa -db /home/ys/Downloads/uniprotdb/database/uniprot_sprot -evalue 1e-5 **-****outfmt** **‘6** **qseqid** **sseqid** **sscinames** **evalue** **pident** **slen** **qstart** **qend** **sstart** **send ’**  -max_target_seqs 1 -num_threads 4 -out ./blast-output_re/LGQ26.blastp &

•报错提示为：

	 Warning: [blastp] Taxonomy name lookup from taxid requires installation of taxdb database with <ftp://ftp.ncbi.nlm.nih.gov/blast/db/taxdb.tar.gz>

很奇怪，并没有要求输出staxid，但总归是关于数据库的问题。

但我移除sscinames 这一项时，程序可以正常跑，不会报错。

所以 我猜想是数据库在格式化的时候出现了问题，或者是数据库不兼容之类的东西。

调整方向：

1、新格式化数据库。 
2、别的参数项来试，既然outfmt为1时可以输出pr的名字，pr名字肯定存在于数据库。

逐一尝试，将`sscinames`换为`stitle`,出现可读的pr名
可用的命令行：
	blastp -query *.fa -db /home/ys/Downloads/uniprotdb/database/uniprot_sprot -evalue 1e-5 -outfmt '6 qseqid sseqide stitle evalue pident slen qstart qend sstart send ' -max_target_seqs 1 -num_threads 4 -out ./blast-output_re/*.blastp  

根据输出结果来看，应该是数据库没有格式化开，在蛋白名的后面多了一些其他的内容
