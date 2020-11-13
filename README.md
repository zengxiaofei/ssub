# ssub

A simple script for submitting jobs on LSF or PBS.

This script is somewhat similar to qsub-sge.pl but without monitor functions.

(懒得用nextflow，重新造了个轮子)

```
$ ssub -h

usage: ssub [-h] [--nlines NLINES] [--dryrun] [--convert {yes,no}]
            [--stringency {low,high}] [--threads THREADS] [--queue QUEUE]
            [--cluster {pbs,lsf}]
            shell_script

-------------------------------------------------------
  A simple script for submitting jobs on LSF or PBS

  Author  :  Xiaofei Zeng
  Email   :  xiaofei_zeng@whu.edu.cn
             zengxf@sustech.edu.cn
  GitHub  :  https://github.com/zengxiaofei/
  Version :  0.95
-------------------------------------------------------

positional arguments:
  shell_script          filename of input shell script, all paths in the script
                        should be either relative paths starting with "./, ../" or
                        absolute paths

optional arguments:
  -h, --help            show this help message and exit
  --nlines NLINES       number of lines in each subscript [default: 1]
  --dryrun              generate subscripts but do not submit them [default: False]
  --convert {yes,no}    convert relative paths to absolute paths [default: yes]
  --stringency {low,high}
                        add "set -e" in each subscript if high [default: high]
  --threads THREADS     number of threads for each subscript [default: 28]
  --queue QUEUE         queue name [default: workq]
  --cluster {pbs,lsf}   cluster name/type [default: pbs]

```

