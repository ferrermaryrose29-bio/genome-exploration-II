# Genome Exploration II — *Homo sapiens* (GRCh38.p14)

## Species and Source
- **Species:** Homo sapiens
- **NCBI Assembly Accession:** GCF_000001405.40 (GRCh38.p14)
- **Assembly Level:** Chromosome / Complete genome (Reference)
- **Genome Source/Database:** NCBI
- **FASTA Filename in Galaxy:** `Homo_sapiens.fasta`
- **Approximate File Size:** 3.3 GB

## Objective
Explore the basic structural properties of the *Homo sapiens* GRCh38.p14 genome
assembly using Galaxy (usegalaxy.org), including summary statistics, sequence-length
distribution, a length-filtering experiment, and a small ORF-finding exercise.

## Tools Used and Key Parameters

| Step | Tool | Key Parameter(s) |
|------|------|-------------------|
| Assembly statistics | Fasta Statistics | Run on full genome FASTA (default settings) |
| Sequence length | Compute sequence length | Output: 2-column tabular (ID, length) |
| Sort | Sort on dataset | Sorted length column, descending |
| Length filtering | Filter sequences by length | Minimum length = 10,000 bp (10 kb) |
| Filtered statistics | Fasta Statistics | Run on filtered (≥10kb) FASTA |
| ORF exploration | EMBOSS getorf | Minimum ORF size ≈ 300 bp |

## Galaxy History
- History name: `Genome_Exploration_II_FERRER_Homo_sapiens`
- https://usegalaxy.org/published/workflow?id=2d67ed7a1dabae7b
## Summary Statistics (Original Genome)
- Number of sequences: 785
- Scaffold N50: 145,136,636 bp
- Scaffold L50: 9
- Scaffold N90: 57,227,416 bp
- Scaffold L90: 22
- Maximum sequence length: 248,956,422 bp
- Mean sequence length: 976 bp
- GC content (overall): 39.64%

See `results_table.md` for the full original-vs-filtered comparison.

## Short Biological Interpretation
The *Homo sapiens* GRCh38.p14 assembly is highly contiguous at the chromosome level:
the longest sequence (chromosome 1) spans 248,956,422 bp, and a Scaffold L50 of only
9 means half the genome is captured within just nine sequences — consistent with a
reference-quality, chromosome-level assembly. However, the total sequence count (785)
and a low mean sequence length (976 bp) show that alongside the 24 main chromosomes,
the assembly includes hundreds of small unplaced/unlocalized scaffolds that add little
to overall genome size but account for most of the sequence count. GC content (39.64%)
falls within the expected range for the human genome. The ORF exploration on a selected
chromosomal region demonstrated that open reading frames can be found readily using a
simple length cutoff (≥300 bp, no internal stop codon), but the exercise also
underscored that an ORF is not evidence of a real gene — confirming an actual gene
requires additional support such as annotation, transcript evidence, or protein
homology, none of which was assessed here.

## Notes
- The original FASTA was never deleted or overwritten; filtering was performed on a copy.
- The filtered assembly (≥10kb) is an educational subset only, not a claim of a
  "better" genome — short sequences can still contain real biological information.
