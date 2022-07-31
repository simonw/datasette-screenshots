# datasette-screenshots

Screenshots of Datasette, taken using [shot-scraper](https://github.com/simonw/shot-scraper).

<!-- [[[cog
import cog, yaml
from pathlib import Path
shots = yaml.safe_load(open("shots.yml"))
for shot in shots:
    cog.out("## {}\n\n".format(shot["output"]))
    cog.out("- Retina: [{output}]({output}) - {size} KB\n".format(
        output=shot["output"],
        size=Path(shot["output"]).stat().st_size // 1024,
    ))
    cog.out("- Non-retina: [non-retina/{output}](non-retina/{output}) - {size} KB\n".format(
        output=shot["output"],
        size=(
            Path("non-retina") / shot["output"]
        ).stat().st_size // 1024,
    ))
    cog.out("\n```yaml\n{}```\n\n".format(yaml.dump([shot])))
    cog.out('<img alt="{output}" src="non-retina/{output}" width="400">\n\n'.format(
        output=shot["output"]
    ))
]]] -->
## global-power-plants.png

- Retina: [global-power-plants.png](global-power-plants.png) - 770 KB
- Non-retina: [non-retina/global-power-plants.png](non-retina/global-power-plants.png) - 238 KB

```yaml
- height: 1600
  output: global-power-plants.png
  url: https://global-power-plants.datasettes.com/global-power-plants/global-power-plants?_facet_size=5&country_long=United+States+of+America
  wait: 5000
```

<img alt="global-power-plants.png" src="non-retina/global-power-plants.png" width="400">

## faceting.png

- Retina: [faceting.png](faceting.png) - 210 KB
- Non-retina: [non-retina/faceting.png](non-retina/faceting.png) - 90 KB

```yaml
- height: 800
  output: faceting.png
  url: https://congress-legislators.datasettes.com/legislators/executive_terms?_facet=type&_facet=party
```

<img alt="faceting.png" src="non-retina/faceting.png" width="400">

## sql-query.png

- Retina: [sql-query.png](sql-query.png) - 169 KB
- Non-retina: [non-retina/sql-query.png](non-retina/sql-query.png) - 73 KB

```yaml
- height: 800
  output: sql-query.png
  url: https://latest.datasette.io/fixtures?sql=%0Aselect+_neighborhood%2C+facet_cities.name%2C+state%0Afrom+facetable%0A++++join+facet_cities%0A++++++++on+facetable._city_id+%3D+facet_cities.id%0Awhere+_neighborhood+like+%27%25%27+%7C%7C+%3Atext+%7C%7C+%27%25%27%0Aorder+by+_neighborhood%3B%0A&text=town
```

<img alt="sql-query.png" src="non-retina/sql-query.png" width="400">

## tutorials-clean-data-locations-map.png

- Retina: [tutorials-clean-data-locations-map.png](tutorials-clean-data-locations-map.png) - 666 KB
- Non-retina: [non-retina/tutorials-clean-data-locations-map.png](non-retina/tutorials-clean-data-locations-map.png) - 253 KB

```yaml
- height: 1200
  output: tutorials-clean-data-locations-map.png
  url: https://manatees.vercel.app/manatees/locations
  wait: 1500
```

<img alt="tutorials-clean-data-locations-map.png" src="non-retina/tutorials-clean-data-locations-map.png" width="400">

## tutorials-clean-data-facets.png

- Retina: [tutorials-clean-data-facets.png](tutorials-clean-data-facets.png) - 160 KB
- Non-retina: [non-retina/tutorials-clean-data-facets.png](non-retina/tutorials-clean-data-facets.png) - 70 KB

```yaml
- output: tutorials-clean-data-facets.png
  selectors:
  - .facet-results
  - header
  url: https://manatees.vercel.app/manatees/locations?_nocol=latitude&_nocol=longitude&_facet=DCODE&_facet=MORTALITY
```

<img alt="tutorials-clean-data-facets.png" src="non-retina/tutorials-clean-data-facets.png" width="400">

<!-- [[[end]]] -->
