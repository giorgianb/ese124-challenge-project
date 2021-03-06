# cplot

## Building
```
git clone https://github.com/giorgianb/cplot
cd cplot
make
```

## Using

If neither `--expression` or `--file` are specified, `cplot` will read and plot
points from standard input. Points are expected in the format `x y`, with any
amount of whitespace in between `x` and `y`. Expressions are functions of `x`.
Several basic functions are also available for use in expressions, namely `sin`,
`cos`, `tan`, `arcsin`, `arccos`, and `ln`.   

`cplot` is highly configurable. The number of ticks an each axis can be
specified using `--x-ticks` and `--y-ticks`. The ranges can be specified using
`--x-min`, `--x-max`, `--y-min`, and `--y-max`. The colors of the axes, x-tick
labels, y-tick labels, and marks can also be configured through command line
options. For the full summary of the available command-line options, see
`./cplot --help`.


## Examples

Plotting `sin(x)`:  
`./cplot --expression "sin(x)" --x-min=-6.28 --x-max=6.28 --y-min=-1 --y-max=1`

Plotting parabolic functions:  
`./cplot --expression "x^2 + 2*x + 1"`

Plotting points from a file:  
`./cplot --file my-data.dat --x-min=-1000 --x-max=1000 --y-min=-40 --y-max=40
--rows=70`

Plotting points from another program:  
`point_generator | ./cplot`

## Help
```
--file, --file=				read and plot points from a file.
--expression, --expression=		generate points from given expression.
--x-min, --x-min=			specify minimum x-value.
--x-max, --x-max=			specify maximum x-value.
--y-min, --y-min=			specify minimum y-value.
--y-max, --y-max=			specify maximum y-value
--x-ticks, --x-ticks=			specify number of x-axis ticks.
--y-ticks, --y-ticks=			specify number of y-axis ticks.
--x-number-color, --x-number-color=	specify color used to print tick labels on x-axis.
--y-number-color, --y-number-color=	specify color used to print tick labels on y-axis.
--axes-color, --axes-color=		specify color used to print axes.
--mark-color, --mark-color=		specify color used to print marks on plot.
--rows, --rows=				specify number of rows y-axis uses.
--columns, --columns=			specify number of columns x-axis uses.
--x-number-width, --x-number-width=	specify width of tick labels on x-axis.
--y-number-width, --y-number-width=	specify width of tick labels on y-axis.
--x-precision, --x-precision=		specify number of decimal points to use when printing x-axis tick labels.
--y-precision, --y-precision=		specify number of decimal points to use when printing y-axis tick labels.
--mark-char, --mark-char=		specify marker character to use on plot.
--help					print this message.


The following colors may be passed to arguments requiring colors:
black red green orange blue purple cyan light-gray dark-gray light-red light-green yellow light-blue light-purple light-cyan white no-color

By default, if neither --file or --expression is specified, points are read from standard input.
```
