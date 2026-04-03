# Pressing Activity vs Pressing Effectiveness
## Barcelona FC — La Liga 2020/21

Tactical analysis of Barcelona's pressing behavior under Ronald Koeman using StatsBomb open event data. This project examines whether pressing volume, location, and effectiveness tell the same story — and what Barcelona's pressing patterns reveal about their third place finish in what was seen as a struggling season.

## Research Question
Does pressing activity and pressing effectiveness differ across match outcomes 
for Barcelona under Koeman — and what does it reveal about their tactical identity?

## Dataset
[StatsBomb Open Data](https://github.com/statsbomb/open-data) — La Liga 2020/21  
- competition_id: 11, season_id: 90
- 35 matches, 139,000+ events
- Full event level data with x/y pitch coordinates
- Includes passes, pressures, duels, interceptions, shots and more

## Approach
1. **Data Loading** — StatsBomb La Liga 2020/21 event data via statsbombpy
2. **Pressing Volume** — Average press count per match across wins, draws and losses
3. **Pressing Location** — Pitch heatmaps showing where Barcelona pressed across results
4. **Opponent Context** — Atletico Madrid comparison across draw and loss
5. **Press Success Rate** — Proportion of press attempts that won the ball back
6. **Counterpress Analysis** — Immediate pressing after losing possession vs organized press

## Key Findings

**Pressing Location mattered more than Pressing Volume**

Barcelona pressed similarly in volume across wins, draws and losses. What differed 
was where and the structure of the press:

- **Wins** — pressing more spread out, slightly more advanced into the opponent's 
  half, more centrally coordinated
- **Draws** — pressing concentrated in the middle third and wings, less penetration 
  into the opponent's half, more passive and reactive
- **Losses** — overall pressing activity drops, coverage in the core center of the 
  pitch minimal, some pressing around the opponent's box suggesting Barcelona were 
  chasing the game

**Press Effectiveness was consistent regardless of result**

Overall press success rate hovered around 15% across wins, draws and losses. Counterpress success rate showed a slight pattern — lowest in losses at 14.2%  vs draws at 19.3% — but differences were not large enough to draw strong causal conclusions.

**Verdict**

For Koeman's Barcelona, pressing location and organization mattered more than pressing volume or effectiveness. Barcelona were not pressing as a unit with clear triggers and zones — they were pressing as individuals reacting to the ball. The problem was tactical structure rather than individual pressing effort — a finding that aligns with their third place finish in a season Atletico Madrid 
won by doing less, but doing it with far more tactical clarity.

## Opponent Context
The Atletico Madrid comparison across Barcelona's draw (GW35, 0-0) and loss 
(GW10, 1-0) confirmed the seen pattern — more structured and centrally 
imposed pressing in the draw, scattered and wing dependent pressing in the loss. 
Keeping the opponent constant strengthened the finding that pressing organization shifted with result rather than opponent quality alone.

## Limitations
- Only 35 of 380 La Liga matches available in StatsBomb free data
- All 35 matches feature Barcelona — no valid cross team comparison possible
- Press success rate measures immediate ball recovery within possession sequences does not capture delayed recoveries or indirect pressing benefits
- Gameweek context and in game scoreline can influence pressing behavior which this analysis does not account for
- Counterpress column in StatsBomb stores NaN for non-counterpresses rather than False — filled with False for analysis

## Tools
- Python 3.13
- statsbombpy
- mplsoccer
- pandas, numpy
- matplotlib, seaborn
