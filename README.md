# Phil Jackson’s 40–20 Rule (NBA)

An R Markdown report that tests Phil Jackson’s “40 wins before 20 losses” contender heuristic using historical NBA game data.

- Main report: `phil_jackson_40_20_rule.Rmd`
- Latest rendered output: `phil_jackson_40_20_rule.html`

## What this report does

- Builds team-season win/loss trajectories from game-level data
- Evaluates whether teams reached **40 wins before 20 losses**
- Focuses on **NBA Finals teams** and highlights exceptions
- Excludes shortened seasons (1998–99 lockout and 2020–21) as caveats

## Requirements

- R (recommended: recent R 4.x)
- Packages: `rmarkdown`, `tidyverse`, `lubridate`, `gt`, `ggplot2`, `scales`
- Pandoc (required by `rmarkdown`)

On macOS (Homebrew):

```bash
brew install pandoc
```

Install R packages:

```r
install.packages(c("rmarkdown","tidyverse","lubridate","gt","ggplot2","scales"), repos = "https://cloud.r-project.org")
```

## Data

This repo expects the dataset CSV in the project root as `Games.csv`.

To keep the repository lightweight and to respect dataset distribution terms, the raw dataset file is not committed by default.

### Data source (citation)

Historical NBA Data and Player Box Scores (Kaggle dataset) by **eoinamoore**:

- https://www.kaggle.com/datasets/eoinamoore/historical-nba-data-and-player-box-scores?resource=download

## How to render

From the project directory:

```r
rmarkdown::render("phil_jackson_40_20_rule.Rmd")
```

This produces `phil_jackson_40_20_rule.html`.
