```R
library(tidyverse)
library(plotly)
library(htmlwidgets)

# Filter data for Machine 1
machine1_data <- X032..1. %>% filter(Machine == 1)

# Create the interactive plot
p <- plot_ly(machine1_data, x = ~Pressure, y = ~PartResistance, color = ~Temperature, 
             type = 'scatter', mode = 'markers', 
             marker = list(size = 8, opacity = 0.8))

p <- p %>% layout(
  title = list(text = 'Effect of Pressure and Temperature on PartResistance (Machine 1)', font = list(size = 18)),
  xaxis = list(title = list(text = 'Pressure', font = list(size = 18)), tickfont = list(size = 14), zeroline = FALSE),
  yaxis = list(title = list(text = 'PartResistance', font = list(size = 18)), tickfont = list(size = 14), zeroline = FALSE),
  paper_bgcolor = '#ffffff', 
  plot_bgcolor = '#ffffff'
)

# Save the plot as an HTML widget
# saveWidget(p, 'media/plots/machine1_partresistance_plot.html', selfcontained = TRUE)
```
