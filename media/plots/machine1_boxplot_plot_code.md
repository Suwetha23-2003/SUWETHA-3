```R
setwd("/content/project")
library(tidyverse)
library(plotly)
library(htmlwidgets)
library(ggplot2)

# Filter data for Machine 1 and convert relevant columns to factors
machine1_data <- X032..1. %>% filter(Machine == 1) %>% 
  mutate(
    Pressure = factor(Pressure),
    Temperature = factor(Temperature)
  )

# Perform ANOVA
anova_result <- aov(PartResistance ~ Pressure * Temperature, data = machine1_data)
print(summary(anova_result))

# Capture Pr(>F) values (code not shown for brevity in saved markdown)

# Create the boxplot using ggplot2
p_boxplot <- ggplot(machine1_data, aes(x = Pressure, y = PartResistance, fill = Temperature)) +
  geom_boxplot() +
  labs(
    title = 'Effect of Pressure and Temperature on PartResistance (Machine 1)',
    x = 'Pressure',
    y = 'PartResistance',
    fill = 'Temperature'
  ) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 18),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text = element_text(size = 14),
    legend.title = element_text(size = 14),
    legend.text = element_text(size = 12),
    panel.background = element_rect(fill = '#ffffff', colour = '#ffffff'),
    plot.background = element_rect(fill = '#ffffff', colour = '#ffffff')
  )

# Convert ggplot to plotly for interactivity
p_interactive <- ggplotly(p_boxplot)

# Save the plot as an HTML widget
# saveWidget(p_interactive, 'media/plots/machine1_boxplot_plot.html', selfcontained = TRUE)
```
