# Original vs. Filtered (≥10 kb) Assembly Statistics — *Homo sapiens* GRCh38.p14

| Metric | Original Genome | After ≥10 kb Filter |
|---|---|---|
| Total length (bp) | 3,298,430,636 | 3,298,430,636 |
| Number of sequences | 785 | 785 |
| Maximum length (bp) | 248,956,422 | 248,956,422 |
| N50 (bp) | 145,136,636 | 145,136,636 |
| L50 | 9 | 9 |
| GC content (%) | 39.84 | 39.84 |

## Filtering Questions

**How many sequences were removed by the 10 kb filter?**
Zero sequences were removed. The filtered dataset still contains all 785 original
sequences, including the shortest one at 976 bp — well below the intended 10,000 bp
cutoff. This indicates the minimum-length parameter in the Filter sequences by length
tool was not actually applied as 10,000 bp in this run, so the step needs to be
re-run with the correct setting to reflect a true ≥10 kb filter.

**Did the total assembly length decrease greatly or only slightly?**
Neither — total assembly length did not decrease at all (stayed at 3,298,430,636 bp),
because no sequences were actually removed by this run of the filter.

**Did N50 change? Why?**
N50 did not change (145,136,636 bp in both). Since N50 is calculated from the same
785 sequences in both datasets, this is expected — N50 would only shift if enough
short sequences were actually excluded to change the length distribution.

**What does this tell you about the contribution of short sequences?**
Because no sequences were filtered out in this run, this dataset can't yet show how
much short sequences contribute to the assembly. Based on the scaffold-length data
seen elsewhere in the assembly, the short unlocalized/unplaced scaffolds are numerous
but individually small, so they likely make up a minor fraction of total genome length
even though they account for most of the sequence count. Re-running the filter
correctly would confirm this directly.
