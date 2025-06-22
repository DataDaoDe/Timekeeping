## Universal Astronomical Cycle Set

|Cycle|Description|
|---|---|
| $c_{\text{day}}$ | Rotation period of a planet |
| $c_{\text{sun}_{i}}$ | Apparent period of Sun $i$ in a binary/trinary system |
| $c_{\text{moon}_{j}}$ | Orbital or synodic period of Moon $j$ |
| $c_{\text{season}_{k}}$ | Seasonal cycle caused by axial tilt or orbit resonance |
| $c_{\text{eclipse}_{s_1, s_2}}$ | Eclipse cycle between stars $s_1$ and $s_2$ |
| $c_{\text{planet}_{p}}$ | Orbital conjunction with other planets or moons |

An analysis framework user can decide which cycles matter, based on cultural, biological or environmental factors.


## A Calendar System

Each calendar $\mathcal{T} \in \mathcal{T}_{cal}$ is a tuple
$$
\mathcal{T} = (C, R, E, F)
$$
where
* C is a finite set $\{ c_i = (P_i, \text{name}_i) \} \subset \mathbb{R}^{+} \times \text{Label}$ representing the set of solar cycles used by the calendar system.
* R is the rule set $\{ r_j : \mathbb{N} \to \mathbb{Q} \}$ for incalation and mapping rules
* $E : \mathbb{R}$ the atomic time, epoch or starting time of the calendar
* $F$ is a display function s.th. $F : \mathbb{R} \to \text{Calendar Units}$.

Further:
* R must be such that the generated calendar covers atomic time $t \in \mathbb{R}^{+}$
* Calendar units typically included decades, years, months, days, hours, etc.

## Astronomical Alignment Score

Let $\mathcal{T}$ be a given calendar (timekeeping system), then the __astronomical alignment score__, $\mathcal{A} : \mathcal{T}_{cal} \to [0, 1]$, is defined by
$$
\mathcal{A}(\mathcal{T}) = 1 - \Delta_{\text{drift}}(\mathcal{T})
$$
where
* $\mathcal{T}_{cal}$ is the set of all valid calendar systems
* $[0, 1] \subset \mathbb{R}$ is an alignment score, where
  * $\mathcal{A}(\mathcal{T}) = 1$ indicates perfect alignment with astronomical cycles
  * $\mathcal{A}(\mathcal{T}) = 0$ indicates total misalignment
*  $\Delta_{\text{drift}}(K)$ is a normalized function capturing long-term misalignment b/t the calendars time units and actual celestial events.


### The Codomain $[0, 1]$

This score reflects how well the calendar aligns with:
* The [tropical solar year](https://en.wikipedia.org/wiki/Tropical_year) (365.242189 days)
* The lunar synodic month (29.530588 days)
* The mean solar day (86,400 seconds)

