### Percentages in ggplot2

Use this syntax to format as percentages:
`scale_x_continuous(labels = scales::percent_format())`
`scale_y_continuous(labels = scales::percent_format())`

To go to x decimal places, use:
`scale_x_continuous(labels = scales::percent_format(accuracy = 0.01))`
`scale_y_continuous(labels = scales::percent_format(accuracy = 0.01))`

### Themes

I usually use `theme_bw()`

List of themes here: https://ggplot2.tidyverse.org/reference/ggtheme.html
