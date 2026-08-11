# Lancet Commission on Investing in Health — Data Dashboard

Interactive dashboard for the Lancet Commission on Investing in Health (CIH),
covering all-cause mortality and life-expectancy decomposition by cause of death.

**Live:** https://omarkarlsson.com/CIH_dash/

## What it shows

**Life expectancy decomposition by cause of death**

- Life expectancy gap compared with the 2019 North Atlantic, by specific cause
- Life expectancy change over time, by specific cause

**All-cause mortality**

- Probability of premature death (PPD)
- Life expectancy (LE)
- Crude mortality rate (CMR) per 1000 population, and per 1000 working-age population
- Probability of death between birth and age *x*, and between age 70 and age *x*
- Age-specific probability of death

Locations and sex are selectable throughout; figures cover countries plus UN
regions, World Bank income groups and other aggregates.

## Data

`data/*.csv` are **aggregated, analysis-ready outputs** at country/region, year,
sex and age level. No restricted microdata is in this repository.

Sources:

- [WHO Global Health Estimates](https://www.who.int/data/global-health-estimates/)
- [UN World Population Prospects](https://population.un.org/wpp/)
- [Human Mortality Database](https://www.mortality.org/)

Methods for the decomposition are described in
[Priority health conditions and life expectancy deficits by cause of death: a life-table decomposition](https://globalhealth2050.org/files/2024/10/Priority-health-conditions-and-life-expectancy-deficits-by-cause-of-death-a-life-table-decomposition.pdf).

## Running it

Plain static HTML, CSS and JavaScript — no build step and no package manager.
Serve the directory over HTTP and open `index.html`; `file://` will not work,
because the browser blocks the CSV fetches.

```
python -m http.server 8000
```

Third-party libraries (d3 v7, noUiSlider, html2canvas) are vendored in
`offlineLib/` rather than loaded from a CDN.

## Related

- [CH2050_dash](https://github.com/O-Karlsson/CH2050_dash) — sibling dashboard for
  the Child Health 2050 project
- [omarkarlsson.com](https://omarkarlsson.com/) — portfolio site that links both
