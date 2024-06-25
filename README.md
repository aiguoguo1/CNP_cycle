#########This database is uesd for the quantification of carbon, nitrogen and phosphorus cycle genes.
#######Using the database requires the args_oap pipeline （https://github.com/xinehc/args_oap）
#####   1. Install the required software
conda install -c bioconda -c conda-forge args_oap
#####   2. Make the customized CNP database
args_oap make_db -i 95CNP.fasta
#####   3. To run the gene quantification using the args_oap pipeline
args_oap stage_one -i input -o output -f fa -t 8 --database 95CNP.fasta
 args_oap stage_two -i output -t 8 --database 95CNP.fasta --structure1 CNPid2gene.txt
