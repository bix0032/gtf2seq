# gtf2seq

__Motivation__: Although tools like snpEFF have been developed for annotating and predicting the effects of variants, there is a lack of tools to show the variants in gene sequences. In order to enable research-ers to easily extract sequences from GFF files with annotations of genomic features, we developped gff2seq to fill this gap. 

Results: Gff2seq, an open-source toolkit, can extract genomic sequences and visualize the genomic features in word document. 


## Installation

### Install using pip (recommended)

Link: https://pypi.org/project/gtf2seq/

```
pip install gtf2seq
```

### Install yourself

```
git clone https://github.com/caoliru/gff2seq.git
pip3 install pyfaidx==0.5.9.5
pip3 install pysam==0.16.0.1
pip3 install python-docx==0.8.10
pip3 install PyVCF==0.6.8
```

## Usage

```
usage: gtf2seq.py [-h] -g GTF -f FASTA -t TRANSCRIPTID_LIST [--vcf VCF]
                  [--sample SAMPLE] [--exclude_intron] [-o OUTPUT]

optional arguments:
  -h, --help            show this help message and exit
  -g GTF, --gtf GTF     Genome annotation file in GTF format
  -f FASTA, --fasta FASTA
                        Genome sequences in FASTA format
  -t TRANSCRIPTID_LIST, --transcriptid_list TRANSCRIPTID_LIST
                        List of transcript IDs
  --vcf VCF             VCF files with snpEff annotation.
  --sample SAMPLE       Sample/individual ID if you want to output genotypes in the sequence for a                                               specific sample/individual.
  --exclude_intron      Exclude intron sequences in the output
  -o OUTPUT, --output OUTPUT
                        Output file in Word format
```

## Example using the test data

```
gtf2seq.py -g test/test.gtf -f test/Zea_mays.B73_RefGen_v4.part.fa -t test/target_transcript_id.txt --vcf test/Mo17_snp.snpEff.part.vcf.gz --sample Zea_mays_Mo17 -o test.docx

```

![](images/example_img.png)


