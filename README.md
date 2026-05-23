Phil Jackson’s 40-20 Rule: Strong Signal, Not Gospel
================

# Introduction

Every NBA spring, once the standings begin to harden and the
championship conversation narrows, Phil Jackson’s most famous
regular-season benchmark comes roaring back into the discourse: a team
must win 40 games before it loses 20 to be taken seriously as a title
threat.

With the 2025-26 playoffs underway, that idea is worth testing as more
than a slogan. If the rule is truly meaningful, it should separate the
league’s elite from the rest of the field and show up consistently among
the teams that actually survive to June.

This report treats the 40-before-20 rule as an empirical claim, not
inherited wisdom. The question is simple: **was Phil Jackson right, or
has the league spent years treating a strong heuristic like a law of
basketball?**

## Data source

This analysis uses the game-level dataset from Kaggle:

- Historical NBA Data and Player Box Scores (by **eoinamoore**)
- <https://www.kaggle.com/datasets/eoinamoore/historical-nba-data-and-player-box-scores?resource=download>

The raw dataset file (`Games.csv`) is expected in the repo root when
rendering, but it is not committed to this repository.

# Analysis

## Statistical frame

A contender filter should do two things well. It should be selective
enough to identify a genuinely narrow class of teams, and it should
appear frequently among the teams we know were real championship
threats.

To keep the analysis historically coherent, the study begins with the
1979-80 season, the first year of the three-point line. That cutoff
matters because it keeps the test inside the modern offensive era most
discussions of the rule already assume.

Two shortened seasons are excluded because the 40-before-20 checkpoint
is not directly comparable to a standard 82-game season:

- **1998-99 (season = 1999):** 50-game lockout season.
- **2020-21 (season = 2021):** 72-game COVID-shortened season.

The point of those exclusions is not to protect the rule. It is to
evaluate the benchmark under a common schedule structure, where “40
before 20” actually describes the same kind of regular-season grind from
year to year.

## Data preparation

The source file is game-level, so every game is expanded into two
team-level observations: one for the home team and one for the away
team. That gives each franchise a chronological season path, allowing
cumulative wins and losses to be tracked game by game.

Seasons are assigned from the date field, with October through December
games mapped to the following season year. From there, the report
filters to regular-season games, removes shortened seasons, and builds
team-season trajectories that can be tested against the Phil Jackson
threshold.

## Method: the 40-20 test

The rule is evaluated within each team-season in chronological order.
For every game, cumulative wins and losses are updated, and a team is
marked as having met the rule if it reaches 40 wins while still sitting
below 20 losses.

To make the result interpretable, the report also captures the first
threshold each team reaches: either 40 wins or 20 losses. That
checkpoint matters because it turns the rule from a vague talking point
into a specific competitive fork in the road.

## Finals teams as the stress test

If the rule is supposed to identify true contenders, the most revealing
test group is not all playoff teams. It is the teams that actually
reached the NBA Finals.

In this dataset, Finals participants are inferred from each season’s
final playoff game and the two teams involved in that matchup. Champions
are then identified as the team with the most Finals wins in that
series.

# Results

## Team-level patterns

Across **45 seasons**, the dataset contains **1255 team-seasons** after
excluding the shortened 1999 and 2021 campaigns. Of those, **192 teams**
reached 40 wins before 20 losses, or **15.3%** of the full population.

That is the first important finding. Only about **15% of all teams**
clear this bar, which means the rule is highly selective by design. It
does not identify “pretty good” teams; it identifies teams that spend
the first 60 games operating at a distinctly elite level.

<div id="uiiyxersuu" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>@import url("https://fonts.googleapis.com/css2?family=Inter:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
#uiiyxersuu table {
  font-family: Inter, 'Source Sans 3', system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#uiiyxersuu thead, #uiiyxersuu tbody, #uiiyxersuu tfoot, #uiiyxersuu tr, #uiiyxersuu td, #uiiyxersuu th {
  border-style: none;
}
&#10;#uiiyxersuu p {
  margin: 0;
  padding: 0;
}
&#10;#uiiyxersuu .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: 100%;
  border-top-style: solid;
  border-top-width: 3px;
  border-top-color: #17408B;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#uiiyxersuu .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}
&#10;#uiiyxersuu .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}
&#10;#uiiyxersuu .gt_heading {
  background-color: #FFFFFF;
  text-align: left;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D9E2EC;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_col_heading {
  color: #333333;
  background-color: #F3F6FA;
  font-size: 100%;
  font-weight: bold;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}
&#10;#uiiyxersuu .gt_column_spanner_outer {
  color: #333333;
  background-color: #F3F6FA;
  font-size: 100%;
  font-weight: bold;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}
&#10;#uiiyxersuu .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#uiiyxersuu .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#uiiyxersuu .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D9E2EC;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}
&#10;#uiiyxersuu .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#uiiyxersuu .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}
&#10;#uiiyxersuu .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}
&#10;#uiiyxersuu .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#uiiyxersuu .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#uiiyxersuu .gt_row {
  padding-top: 6px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #E6ECF2;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}
&#10;#uiiyxersuu .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#uiiyxersuu .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}
&#10;#uiiyxersuu .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#uiiyxersuu .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#uiiyxersuu .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#uiiyxersuu .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#uiiyxersuu .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#uiiyxersuu .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_striped {
  background-color: #FAFBFD;
}
&#10;#uiiyxersuu .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#uiiyxersuu .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#uiiyxersuu .gt_sourcenote {
  font-size: 11px;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#uiiyxersuu .gt_left {
  text-align: left;
}
&#10;#uiiyxersuu .gt_center {
  text-align: center;
}
&#10;#uiiyxersuu .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#uiiyxersuu .gt_font_normal {
  font-weight: normal;
}
&#10;#uiiyxersuu .gt_font_bold {
  font-weight: bold;
}
&#10;#uiiyxersuu .gt_font_italic {
  font-style: italic;
}
&#10;#uiiyxersuu .gt_super {
  font-size: 65%;
}
&#10;#uiiyxersuu .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#uiiyxersuu .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#uiiyxersuu .gt_indent_1 {
  text-indent: 5px;
}
&#10;#uiiyxersuu .gt_indent_2 {
  text-indent: 10px;
}
&#10;#uiiyxersuu .gt_indent_3 {
  text-indent: 15px;
}
&#10;#uiiyxersuu .gt_indent_4 {
  text-indent: 20px;
}
&#10;#uiiyxersuu .gt_indent_5 {
  text-indent: 25px;
}
&#10;#uiiyxersuu .katex-display {
  display: inline-flex !important;
  margin-bottom: 0.75em !important;
}
&#10;#uiiyxersuu div.Reactable > div.rt-table > div.rt-thead > div.rt-tr.rt-tr-group-header > div.rt-th-group:after {
  height: 0px !important;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="2" class="gt_heading gt_title gt_font_normal" style><span class='gt_from_md'><strong>40-Before-20 Scorecard</strong></span></td>
    </tr>
    <tr class="gt_heading">
      <td colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>Three-point era only (1980 onward), excluding the shortened 1999 and 2021 seasons</td>
    </tr>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="metric">Metric</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1" scope="col" id="value">Result</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="metric" class="gt_row gt_left">Seasons analyzed</td>
<td headers="value" class="gt_row gt_right">45</td></tr>
    <tr><td headers="metric" class="gt_row gt_left">Total team-seasons</td>
<td headers="value" class="gt_row gt_right">1255</td></tr>
    <tr><td headers="metric" class="gt_row gt_left">Teams that met 40-before-20</td>
<td headers="value" class="gt_row gt_right">192</td></tr>
    <tr><td headers="metric" class="gt_row gt_left">Share of all team-seasons that met the rule</td>
<td headers="value" class="gt_row gt_right">15.3%</td></tr>
    <tr><td headers="metric" class="gt_row gt_left">Finals teams</td>
<td headers="value" class="gt_row gt_right">90</td></tr>
    <tr><td headers="metric" class="gt_row gt_left">Finals teams that met the rule</td>
<td headers="value" class="gt_row gt_right">69</td></tr>
    <tr><td headers="metric" class="gt_row gt_left">Share of Finals teams that met the rule</td>
<td headers="value" class="gt_row gt_right">76.7%</td></tr>
  </tbody>
  &#10;</table>
</div>

## Finals teams

Among **90 Finals teams**, **69** met the benchmark, which works out to
**76.7%**. That is strong evidence in Phil Jackson’s favor: most teams
that survive to the championship round do, in fact, clear the threshold.

But that does not make the rule absolute. Finals teams are already an
elite subset, and the more revealing question is not whether many of
them pass the test. It is whether the rule misses anyone who was good
enough to get all the way to June anyway.

Here is the cleanest read of the findings:

- **Selective benchmark:** only about 15% of all team-seasons qualify.
- **Strong contender signal:** most Finals teams do qualify.
- **Not a law:** some Finals teams miss the benchmark, and a few of them
  still win the championship.

<div id="ccbwpvmrkz" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>@import url("https://fonts.googleapis.com/css2?family=Inter:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
#ccbwpvmrkz table {
  font-family: Inter, 'Source Sans 3', system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#ccbwpvmrkz thead, #ccbwpvmrkz tbody, #ccbwpvmrkz tfoot, #ccbwpvmrkz tr, #ccbwpvmrkz td, #ccbwpvmrkz th {
  border-style: none;
}
&#10;#ccbwpvmrkz p {
  margin: 0;
  padding: 0;
}
&#10;#ccbwpvmrkz .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: 100%;
  border-top-style: solid;
  border-top-width: 3px;
  border-top-color: #17408B;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#ccbwpvmrkz .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}
&#10;#ccbwpvmrkz .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}
&#10;#ccbwpvmrkz .gt_heading {
  background-color: #FFFFFF;
  text-align: left;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D9E2EC;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_col_heading {
  color: #333333;
  background-color: #F3F6FA;
  font-size: 100%;
  font-weight: bold;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}
&#10;#ccbwpvmrkz .gt_column_spanner_outer {
  color: #333333;
  background-color: #F3F6FA;
  font-size: 100%;
  font-weight: bold;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}
&#10;#ccbwpvmrkz .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#ccbwpvmrkz .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#ccbwpvmrkz .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D9E2EC;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}
&#10;#ccbwpvmrkz .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#ccbwpvmrkz .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}
&#10;#ccbwpvmrkz .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}
&#10;#ccbwpvmrkz .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#ccbwpvmrkz .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#ccbwpvmrkz .gt_row {
  padding-top: 6px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #E6ECF2;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}
&#10;#ccbwpvmrkz .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ccbwpvmrkz .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}
&#10;#ccbwpvmrkz .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#ccbwpvmrkz .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#ccbwpvmrkz .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ccbwpvmrkz .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#ccbwpvmrkz .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ccbwpvmrkz .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_striped {
  background-color: #FAFBFD;
}
&#10;#ccbwpvmrkz .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ccbwpvmrkz .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#ccbwpvmrkz .gt_sourcenote {
  font-size: 11px;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#ccbwpvmrkz .gt_left {
  text-align: left;
}
&#10;#ccbwpvmrkz .gt_center {
  text-align: center;
}
&#10;#ccbwpvmrkz .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#ccbwpvmrkz .gt_font_normal {
  font-weight: normal;
}
&#10;#ccbwpvmrkz .gt_font_bold {
  font-weight: bold;
}
&#10;#ccbwpvmrkz .gt_font_italic {
  font-style: italic;
}
&#10;#ccbwpvmrkz .gt_super {
  font-size: 65%;
}
&#10;#ccbwpvmrkz .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#ccbwpvmrkz .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#ccbwpvmrkz .gt_indent_1 {
  text-indent: 5px;
}
&#10;#ccbwpvmrkz .gt_indent_2 {
  text-indent: 10px;
}
&#10;#ccbwpvmrkz .gt_indent_3 {
  text-indent: 15px;
}
&#10;#ccbwpvmrkz .gt_indent_4 {
  text-indent: 20px;
}
&#10;#ccbwpvmrkz .gt_indent_5 {
  text-indent: 25px;
}
&#10;#ccbwpvmrkz .katex-display {
  display: inline-flex !important;
  margin-bottom: 0.75em !important;
}
&#10;#ccbwpvmrkz div.Reactable > div.rt-table > div.rt-thead > div.rt-tr.rt-tr-group-header > div.rt-th-group:after {
  height: 0px !important;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="9" class="gt_heading gt_title gt_font_normal" style><span class='gt_from_md'><strong>Finals Teams Who Missed 40-20</strong></span></td>
    </tr>
    <tr class="gt_heading">
      <td colspan="9" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>Teams that reached 20 losses before 40 wins and still advanced to the NBA Finals</td>
    </tr>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="season">Season</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="finalist_teamName">Finals Team</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="won_title">Won Title</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="wins_at_threshold">Wins at Threshold</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="losses_at_threshold">Losses at Threshold</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="threshold_type">Threshold</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="final_wins">Final Wins</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="final_losses">Final Losses</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="reached_40_before_20">Met 40-20</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="season" class="gt_row gt_center">1981</td>
<td headers="finalist_teamName" class="gt_row gt_left">Rockets</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">14</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">40</td>
<td headers="final_losses" class="gt_row gt_center">42</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">1984</td>
<td headers="finalist_teamName" class="gt_row gt_left">Lakers</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">38</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">54</td>
<td headers="final_losses" class="gt_row gt_center">28</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">1986</td>
<td headers="finalist_teamName" class="gt_row gt_left">Rockets</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">35</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">51</td>
<td headers="final_losses" class="gt_row gt_center">31</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">1988</td>
<td headers="finalist_teamName" class="gt_row gt_left">Pistons</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">38</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">54</td>
<td headers="final_losses" class="gt_row gt_center">28</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">1995</td>
<td headers="finalist_teamName" class="gt_row gt_left">Rockets</td>
<td headers="won_title" class="gt_row gt_center">Yes</td>
<td headers="wins_at_threshold" class="gt_row gt_center">35</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">47</td>
<td headers="final_losses" class="gt_row gt_center">35</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2002</td>
<td headers="finalist_teamName" class="gt_row gt_left">Nets</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">39</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">52</td>
<td headers="final_losses" class="gt_row gt_center">30</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2003</td>
<td headers="finalist_teamName" class="gt_row gt_left">Nets</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">37</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">49</td>
<td headers="final_losses" class="gt_row gt_center">33</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2004</td>
<td headers="finalist_teamName" class="gt_row gt_left">Pistons</td>
<td headers="won_title" class="gt_row gt_center">Yes</td>
<td headers="wins_at_threshold" class="gt_row gt_center">33</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">54</td>
<td headers="final_losses" class="gt_row gt_center">28</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2004</td>
<td headers="finalist_teamName" class="gt_row gt_left">Lakers</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">36</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">56</td>
<td headers="final_losses" class="gt_row gt_center">26</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2005</td>
<td headers="finalist_teamName" class="gt_row gt_left">Pistons</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">36</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">54</td>
<td headers="final_losses" class="gt_row gt_center">28</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2006</td>
<td headers="finalist_teamName" class="gt_row gt_left">Heat</td>
<td headers="won_title" class="gt_row gt_center">Yes</td>
<td headers="wins_at_threshold" class="gt_row gt_center">30</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">52</td>
<td headers="final_losses" class="gt_row gt_center">30</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2007</td>
<td headers="finalist_teamName" class="gt_row gt_left">Cavaliers</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">26</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">50</td>
<td headers="final_losses" class="gt_row gt_center">32</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2010</td>
<td headers="finalist_teamName" class="gt_row gt_left">Celtics</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">36</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">50</td>
<td headers="final_losses" class="gt_row gt_center">32</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2015</td>
<td headers="finalist_teamName" class="gt_row gt_left">Cavaliers</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">19</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">53</td>
<td headers="final_losses" class="gt_row gt_center">29</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2018</td>
<td headers="finalist_teamName" class="gt_row gt_left">Cavaliers</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">29</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">50</td>
<td headers="final_losses" class="gt_row gt_center">32</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2020</td>
<td headers="finalist_teamName" class="gt_row gt_left">Heat</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">35</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">44</td>
<td headers="final_losses" class="gt_row gt_center">29</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2022</td>
<td headers="finalist_teamName" class="gt_row gt_left">Celtics</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">18</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">51</td>
<td headers="final_losses" class="gt_row gt_center">31</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2023</td>
<td headers="finalist_teamName" class="gt_row gt_left">Heat</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">21</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">44</td>
<td headers="final_losses" class="gt_row gt_center">38</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2024</td>
<td headers="finalist_teamName" class="gt_row gt_left">Mavericks</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">24</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">48</td>
<td headers="final_losses" class="gt_row gt_center">30</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2025</td>
<td headers="finalist_teamName" class="gt_row gt_left">Pacers</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">24</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">50</td>
<td headers="final_losses" class="gt_row gt_center">32</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2026</td>
<td headers="finalist_teamName" class="gt_row gt_left">Timberwolves</td>
<td headers="won_title" class="gt_row gt_center">No</td>
<td headers="wins_at_threshold" class="gt_row gt_center">31</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">49</td>
<td headers="final_losses" class="gt_row gt_center">33</td>
<td headers="reached_40_before_20" class="gt_row gt_center">No</td></tr>
  </tbody>
  <tfoot>
    <tr class="gt_sourcenotes">
      <td class="gt_sourcenote" colspan="9"><span class='gt_from_md'>Threshold record captures the first moment a team hit either <strong>40 wins</strong> or <strong>20 losses</strong>.</span></td>
    </tr>
  </tfoot>
</table>
</div>

This table is where the rule starts to bend. These are the teams that
reached **20 losses before 40 wins** and still found a path to the
Finals, which makes them the most important exceptions in the report.

## Champions and the rule

To translate the rule into championship terms, the chart below compares
title winners that met the benchmark with title winners that did not.

<img src="/Users/ayushgupta/Desktop/40-20 Rule/README_files/figure-gfm/plot-champions-40-20-pie-1.png" width="92%" style="display: block; margin: auto;" />

A chart like this is useful because it keeps the argument disciplined.
The benchmark clearly aligns with championship caliber most of the time,
but not all of the time. That distinction is the heart of the report:
the rule is powerful as a signal, weaker as a guarantee.

<div id="xrpypyrjwr" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>@import url("https://fonts.googleapis.com/css2?family=Inter:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
#xrpypyrjwr table {
  font-family: Inter, 'Source Sans 3', system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#xrpypyrjwr thead, #xrpypyrjwr tbody, #xrpypyrjwr tfoot, #xrpypyrjwr tr, #xrpypyrjwr td, #xrpypyrjwr th {
  border-style: none;
}
&#10;#xrpypyrjwr p {
  margin: 0;
  padding: 0;
}
&#10;#xrpypyrjwr .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: 100%;
  border-top-style: solid;
  border-top-width: 3px;
  border-top-color: #17408B;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#xrpypyrjwr .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}
&#10;#xrpypyrjwr .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}
&#10;#xrpypyrjwr .gt_heading {
  background-color: #FFFFFF;
  text-align: left;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D9E2EC;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_col_heading {
  color: #333333;
  background-color: #F3F6FA;
  font-size: 100%;
  font-weight: bold;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}
&#10;#xrpypyrjwr .gt_column_spanner_outer {
  color: #333333;
  background-color: #F3F6FA;
  font-size: 100%;
  font-weight: bold;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}
&#10;#xrpypyrjwr .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#xrpypyrjwr .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#xrpypyrjwr .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D9E2EC;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}
&#10;#xrpypyrjwr .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#xrpypyrjwr .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}
&#10;#xrpypyrjwr .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}
&#10;#xrpypyrjwr .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#xrpypyrjwr .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#xrpypyrjwr .gt_row {
  padding-top: 6px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #E6ECF2;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}
&#10;#xrpypyrjwr .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#xrpypyrjwr .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}
&#10;#xrpypyrjwr .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#xrpypyrjwr .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#xrpypyrjwr .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#xrpypyrjwr .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#xrpypyrjwr .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#xrpypyrjwr .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_striped {
  background-color: #FAFBFD;
}
&#10;#xrpypyrjwr .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#xrpypyrjwr .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#xrpypyrjwr .gt_sourcenote {
  font-size: 11px;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#xrpypyrjwr .gt_left {
  text-align: left;
}
&#10;#xrpypyrjwr .gt_center {
  text-align: center;
}
&#10;#xrpypyrjwr .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#xrpypyrjwr .gt_font_normal {
  font-weight: normal;
}
&#10;#xrpypyrjwr .gt_font_bold {
  font-weight: bold;
}
&#10;#xrpypyrjwr .gt_font_italic {
  font-style: italic;
}
&#10;#xrpypyrjwr .gt_super {
  font-size: 65%;
}
&#10;#xrpypyrjwr .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#xrpypyrjwr .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#xrpypyrjwr .gt_indent_1 {
  text-indent: 5px;
}
&#10;#xrpypyrjwr .gt_indent_2 {
  text-indent: 10px;
}
&#10;#xrpypyrjwr .gt_indent_3 {
  text-indent: 15px;
}
&#10;#xrpypyrjwr .gt_indent_4 {
  text-indent: 20px;
}
&#10;#xrpypyrjwr .gt_indent_5 {
  text-indent: 25px;
}
&#10;#xrpypyrjwr .katex-display {
  display: inline-flex !important;
  margin-bottom: 0.75em !important;
}
&#10;#xrpypyrjwr div.Reactable > div.rt-table > div.rt-thead > div.rt-tr.rt-tr-group-header > div.rt-th-group:after {
  height: 0px !important;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="9" class="gt_heading gt_title gt_font_normal" style><span class='gt_from_md'><strong>Champions Who Missed 40-20</strong></span></td>
    </tr>
    <tr class="gt_heading">
      <td colspan="9" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>The strongest evidence against treating the Phil Jackson rule as a hard law</td>
    </tr>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="season">Season</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="finalist_teamName">Champion</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="won_title">won_title</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="wins_at_threshold">Wins at Threshold</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="losses_at_threshold">Losses at Threshold</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" scope="col" id="threshold_type">Threshold</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="final_wins">Final Wins</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="final_losses">Final Losses</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1" scope="col" id="reached_40_before_20">reached_40_before_20</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="season" class="gt_row gt_center">1995</td>
<td headers="finalist_teamName" class="gt_row gt_left">Rockets</td>
<td headers="won_title" class="gt_row gt_center">TRUE</td>
<td headers="wins_at_threshold" class="gt_row gt_center">35</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">47</td>
<td headers="final_losses" class="gt_row gt_center">35</td>
<td headers="reached_40_before_20" class="gt_row gt_center">FALSE</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2004</td>
<td headers="finalist_teamName" class="gt_row gt_left">Pistons</td>
<td headers="won_title" class="gt_row gt_center">TRUE</td>
<td headers="wins_at_threshold" class="gt_row gt_center">33</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">54</td>
<td headers="final_losses" class="gt_row gt_center">28</td>
<td headers="reached_40_before_20" class="gt_row gt_center">FALSE</td></tr>
    <tr><td headers="season" class="gt_row gt_center">2006</td>
<td headers="finalist_teamName" class="gt_row gt_left">Heat</td>
<td headers="won_title" class="gt_row gt_center">TRUE</td>
<td headers="wins_at_threshold" class="gt_row gt_center">30</td>
<td headers="losses_at_threshold" class="gt_row gt_center">20</td>
<td headers="threshold_type" class="gt_row gt_left">20 losses</td>
<td headers="final_wins" class="gt_row gt_center">52</td>
<td headers="final_losses" class="gt_row gt_center">30</td>
<td headers="reached_40_before_20" class="gt_row gt_center">FALSE</td></tr>
  </tbody>
  <tfoot>
    <tr class="gt_sourcenotes">
      <td class="gt_sourcenote" colspan="9"><span class='gt_from_md'>These teams won the title despite reaching <strong>20 losses before 40 wins</strong>.</span></td>
    </tr>
  </tfoot>
</table>
</div>

If there is one section that prevents the rule from being treated as
gospel, it is this one. The **1995 Rockets**, **2004 Pistons**, and
**2006 Heat** are not trivia answers; they are championship
counterexamples that force a more careful interpretation of the rule.

# Visuals

## Finals exceptions outcome

<img src="/Users/ayushgupta/Desktop/40-20 Rule/README_files/figure-gfm/plot-finals-pie-1.png" width="92%" style="display: block; margin: auto;" />

This chart narrows the lens to the teams that failed the benchmark but
still reached the Finals. In this sample, only **14%** of those
exception teams went on to win the title, which reinforces an important
point: breaking the rule does not eliminate a team, but it usually
leaves less margin for error.

## Finals winners: wins at 20 losses

<img src="/Users/ayushgupta/Desktop/40-20 Rule/README_files/figure-gfm/plot-finals-winners-hist-1.png" width="92%" style="display: block; margin: auto;" />

This is the clearest visual rebuttal to a literal reading of the rule.
The three championship exceptions were all below the line when loss
number 20 arrived, which means Phil Jackson’s benchmark would have
screened out teams that ultimately proved good enough to win the title
anyway.

# Verdict

Phil Jackson was **mostly right** about what the 40-before-20 rule
captures. It is a sharp contender filter, and the selectivity matters:
only about 15% of all team-seasons reach that standard, while most
Finals teams do.

But the benchmark breaks the moment it is treated as a hard law.
Championship exceptions exist, and they are not marginal edge cases.
They are title teams that remind us how much playoff success depends on
factors the rule cannot see: health, matchup leverage, roster changes,
star-level shot creation, defensive adaptability, and late-season
improvement.

The best interpretation is the most disciplined one. **40-before-20 is a
strong signal of contender quality, not a guarantee of who gets the
trophy in June.**
