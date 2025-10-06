mkdir GA3
cd GA3
touch README.md
mkdir data scripts results
cp -v ../garrigos-data/fastq/ERR10802863* data/
cp -v ../garrigos-data/meta/metadata.tsv data/
git init
echo "data/" > .gitignore
echo "results/" >> git ignore
git add README.md
git commit -m "Completed part A"

## PART B

touch scripts/echo.sh
bash scripts/echo.sh Oct07 Oct08
bash scripts/echo.sh Oct07 Oct08 Oct09 Oct10
bash scripts/echo.sh Oct07 Oct08 "Oct09 Oct10"

touch scripts/concat.sh
bash scripts/concat.sh data/ERR10802863_R1.fastq.gz data/ERR10802863_R2.fastq.gz results/combined_file.fastq.gz

touch scripts/printline.sh
bash scripts/printline.sh data/metadata.tsv 10
bash scripts/printlinesh data/metadata.tsv 15 > results/line_15

metadata-metadata.tsv
line_number-15

bash scripts/printlinesh data/"$metadata" "$line_number" > results/"$metadata"_"$line_number"

apptainer exec oras://community.wave.seqera.io/library/trim-galore:0.6.10--bc38c9238980c80e -v

apptainer exec oras://community.wave.seqera.io/library/trim-galore:0.5.0--16bd677ee493f6cd -v

pandoc -v
module spider pandoc
module load pandoc/3.6.4

pandoc -o README.pdf README.md

git remote add origin git@github.com:kstarr791/GA3.git
git commit -m "finished"
git branch -M main
git push -u origin main

