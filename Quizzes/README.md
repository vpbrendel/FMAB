# FMAB/Quizzes

Understanding, let alone mastery, of much of the background as well as the domain-specific material of [FMAB](../README.md) requires solving lots of exercises and problems.
The textbook includes selected domain-specific exercises and problems which seek to enhance understanding of the text and explore further directions.
The [FMAB Quizzes](./README.md) repository provides a large and growing number of additional exercises, with particular focus on background material.

Questions are labeled by subject and difficulty, and include, for example, simple questions probing the students' skills of using a UNIX-based computer or their knowledge of basic statistics.
All questions (and answers) are derived from a structured file in [YAML](http://yaml.org) format.

Let's pull two random examples from the library.
First type

```bash
python src/xmkquiz.py -h
```

which gives the usage help

```bash
usage: xmkquiz.py [-h] [--lib FILE] [--out FILE] [--answers FILE] [--sub W]
                  [--subsub X] [--type Y] [--diff Z] [--rand N]

Generate a quiz from the provided question library

optional arguments:
  -h, --help      show this help message and exit
  --lib FILE      question library file (default: "../data/FMABqlib.yml")
  --out FILE      output file (default: stdout)
  --answers FILE  write answers to specified file
  --sub W         filter by subject
  --subsub X      filter by sub-subject
  --type Y        filter by question type
  --diff Z        filter by difficulty
  --rand N        select a random sample of N questions matching the specified
                  filtering criteria
```

Now,
```bash
python src/xmkquiz.py --lib data/FMABqlib.yml --rand 2
```

with sample output

```text
1. Explain what the following command does:

   ls *.pl | wc -l

2. If your current directory is `/home/alice/projects/dna-seq/` and you
   invoke the command `cd ../alignment/smith-waterman/`, what is your current
   directory now? Please provide the full absolute path.
```

Notes:
python src/xmkquiz.py --lib data/FMABqlib.yml > myquiz.md
pandoc -f markdown -t latex -o myquiz.pdf  myquiz.md
evince myquiz.pdf
