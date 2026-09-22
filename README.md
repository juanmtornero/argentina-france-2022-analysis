# Argentina vs France — 2022 FIFA World Cup Final

## Ball Progression and Chance Creation Analysis

This project analyzes how Argentina progressed the ball and created scoring opportunities against France in the 2022 FIFA World Cup Final.

Using **StatsBomb Open Data**, the analysis explores the relationship between ball progression, final-third entries and shot creation.

---

## Objective

The main question behind the project is:

**How did Argentina progress the ball and create attacking opportunities against France?**

The analysis focuses on:

- Shot production and chance quality
- Progressive passing
- Ball progression from the center-backs
- Progressive passing connections
- Final-third entries
- Chance creation after entering the final third

---

## Data

**Source:** StatsBomb Open Data  
**Competition:** FIFA World Cup 2022  
**Match:** Argentina vs France — Final  
**StatsBomb Match ID:** `3869685`

StatsBomb uses a **120 x 80 coordinate system**, with the attacking goal centered approximately at `(120, 40)`.

---

## Tools

- Python
- pandas
- NumPy
- Matplotlib
- mplsoccer
- statsbombpy

---

## Methodology

### Progressive Pass

For this project, a completed pass is considered progressive when it reduces the distance to the opposition goal by at least **10 StatsBomb units**.

This is a simplified project-specific definition used to identify meaningful territorial progression.

### Final-Third Entry

A completed pass is classified as a final-third entry when:

- it starts outside the final third (`x < 80`)
- and ends inside the final third (`x >= 80`)

---

## Key Findings

### 1. Argentina produced greater attacking output

Argentina generated more shots than France during the match and produced substantially more non-penalty expected goals.

This provided the starting point for investigating how Argentina created those attacking situations.

---

### 2. Cristian Romero played an important role in progression from defense

Despite Nicolás Otamendi completing more passes overall:

- **Otamendi:** 69 completed passes
- **Romero:** 60 completed passes

Romero completed considerably more progressive passes:

- **Romero:** 24 progressive passes — 40% of completed passes
- **Otamendi:** 9 progressive passes — 13%

Their pass maps also showed different spatial patterns, with Romero displaying a more vertical progression profile and several changes of orientation.

---

### 3. Enzo Fernández and Lionel Messi were key progression hubs

Argentina's progressive passing network highlighted **Enzo Fernández and Lionel Messi** as important connecting points.

Enzo frequently received progressive passes from deeper players and continued progression toward more advanced teammates.

The **Romero → Enzo** connection was the most frequent progressive passing connection in the network.

Messi displayed a similar role further up the pitch, both receiving and generating progressive passes.

---

### 4. Player roles differed between progressive pass generation and reception

The progressive passes sent-vs-received analysis revealed a clear positional pattern.

- Cristian Romero showed the strongest progression-generating profile.
- Julián Álvarez appeared primarily as a receiver of progressive passes.
- Enzo Fernández and Lionel Messi combined high volumes of both sent and received progressive passes.

Deeper players generally generated more progressive passes, while advanced players tended to receive them.

---

### 5. Argentina frequently entered the final third through wide areas

Argentina completed **36 passes into the final third across 31 possessions**.

The spatial distribution of these passes showed a strong tendency to access advanced areas through the wide channels rather than directly through central areas.

Most final-third entries also originated after Argentina had already established possession in the opposition half.

---

### 6. Final-third entries were strongly associated with chance creation

Of the **31 possessions** containing a completed pass into the final third:

- **11 possessions** produced at least one subsequent shot
- those possessions generated **13 shots**

These shots represented:

- **68.4% of Argentina's non-penalty shots**
- **82.6% of Argentina's total npxG**

Their average chance quality was also higher:

- **After final-third pass entry:** 0.125 npxG per shot
- **Other non-penalty shots:** 0.057 npxG per shot

This suggests that final-third pass entries were associated not only with greater shot volume, but also with higher-quality chances in this match.

---

## Conclusion

Argentina's attacking progression against France showed a clear structure.

Ball progression frequently began from deeper players such as Cristian Romero, continued through important connectors such as Enzo Fernández and Lionel Messi, and often reached the final third through wide areas.

Final-third pass entries were also closely associated with Argentina's chance creation, accounting for a large majority of the team's non-penalty expected goals.

Overall, the analysis illustrates how event data can be used to connect **ball progression, player roles, territorial advancement and shot creation** within a single match.

---

## Limitations

This project analyzes only one match and should not be interpreted as a general description of Argentina's tactical identity.

The progressive-pass definition is a simplified analytical choice and naturally favors players operating from deeper positions, who have more distance available to progress toward goal.

Final-third entries only include completed passes crossing the `x = 80` threshold and do not capture other forms of progression such as:

- carries
- recoveries inside the final third
- throw-ins
- possessions beginning inside the final third

---

## Repository Structure

```text
argentina-france-2022-analysis/
│
├── Argentina_France_2022_Portfolio.ipynb
├── README.md
└── requirements.txt
