# matplotlib-backend-kitty

This python module allows you to use your
[kitty terminal](https://github.com/kovidgoyal/kitty)
to show the plots generated by python's
[Matplotlib](https://github.com/matplotlib/matplotlib).

To use it, add the module to your `$PYTHONPATH` and
initialize matplotlib like this:

```python
import matplotlib
matplotlib.use('module://matplotlib-backend-kitty')
import matplotlib.pyplot as plt
```

You can then test it from kitty with something like
`>>> import pandas; pandas.Series(range(10)).plot()`.

It's based on the way that the IPython Matplatlib
output works: it's a hybrid of both image and GUI backends,
piping the Agg Backend's output to kitty's `icat` kitten.
This means that both `DataFrame.plot()` and `plt.show()`
will work as expected, but that the image drawn on your
terminal isn't interactive, and animations aren't supported.
