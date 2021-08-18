# pedalart - manipulate pedigree files

In the analysis of inherited traits - particularly disease - we often rely on having a slice of the family tree, or *pedigree* which shows individuals and their relationships to one another. There is a commonly used file format for [PED files](https://gatk.broadinstitute.org/hc/en-us/articles/360035531972-PED-Pedigree-format) which gives a machine readable form of this information, which is often shown graphically. This machine readable form, while convenient for machines, is not very intuative for humans, either to read, or to write. There are some very nice graphical tools for allowing us to visualise and edit these files, but none that are convenient for working with plain text environments such as Markdown.

This Python tool provides a simple ascii representation of the information which allows you to convert between an *ascii art* representation, and a PED representation.

For example, consider the following PED file:
```
1   1   0  0  1  1
1   2   0  0  2  1
1   3   0  0  1  1
1   4   1  2  2  1
1   5   3  4  2  2
1   6   3  4  1  2
```
can be rendered as
```
       xy--+--xx
           |
    xy--+--xx
        |
     +--+--+
     |     |
    XX     XY
```

## Format

- Chromosomal sex is denoted as `xx`, `xy` (or `uu` for unknown).
- Unaffected individuals are denoted with lower case letters.
- Affected individuals are denoted with upper case letters.
