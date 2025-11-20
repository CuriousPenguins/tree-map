🌳 Annex Tree Map

Community-Sourced Urban Forest Data for Toronto’s Annex Neighbourhood
https://annextrees.xyz.am

https://annextreemap.xyz.am/

📍 Overview

The Annex Tree Map is a community-driven project to visualize, maintain, and expand the historical tree inventory collected in Toronto’s Annex neighbourhood between 2010 and 2014.

Originally surveyed by neighbourhood volunteers through the Annex Residents’ Association (ARA), this dataset documents tree species, DBH, height, condition notes, and geographic coordinates for thousands of trees.

This repository hosts:

The cleaned and community-maintained dataset (annex-trees.json)

A Leaflet-based interactive map

A Bootstrap 5 “About the Project” page

Tools for generating new GeoJSON entries

Community guidelines for contributions

🌐 Live Sites
1. Project Homepage & Documentation

📄 https://annextrees.xyz.am

Contains project info, data history, contribution guide, JSON generator, and more.

2. Interactive Map

🗺️ https://annextreemap.xyz.am

An OpenStreetMap + Leaflet map that displays all trees and supports filtering by:

Species

Street

Tree size (DBH ranges)

🌲 Data Source & Credits

The dataset originates from the Annex Residents’ Association (ARA) Tree Mapping Project (2010–2014).
Volunteers collected:

Tree species

Street address

DBH (Diameter at Breast Height)

Height

Number of stems

Comments

Geographic coordinates

Original dataset was published via the ARA website and exported as GeoJSON.

This repository preserves the data and provides tools for curation, correction, and expansion.

📁 Repo Structure
/data
   annex-trees.json     → Main GeoJSON dataset

README.md               → You are here

🛠️ Contributing

We welcome pull requests for:

Fixing incorrect coordinates

Correcting tree heights or DBH anomalies

Adding missing street names

Cleaning species names

Adding new tree observations

Improving map functionality

1. Fixing Data

If you spot errors:

Open an Issue

Describe the problem (tree_no, location, expected value)

Submit a Pull Request with the fix

🧰 Adding New Trees (JSON Generator)

Visit:

➡️ https://annextrees.xyz.am

Scroll to the JSON Generator tool.

It will output a properly formatted GeoJSON fragment like:

```html

{
  "type": "Feature",
  "properties": {
    "Date": "2024",
    "tree_no": "987",
    "house_number": "42",
    "street_code": "Kendal Ave",
    "species_code": "acrsac",
    "tree_name": "Sugar Maple",
    "n_o_s": "1.0",
    "DBH": "28.0",
    "total_height": "8.5",
    "Comments": "",
    "X coordinate": -79.405501,
    "Y coordinate": 43.673770
  },
  "geometry": {
    "type": "Point",
    "coordinates": [ -79.405501, 43.673770 ]
  }
}
```

Paste this directly into annex-trees.json.

Need coordinates?
Use the companion tool:
📌 https://coordinates.xyz.am

🔗 Embedding the Map

You can embed the tree map in any site using:

```html
<iframe
  src="https://annextreemap.xyz.am/"
  width="100%"
  height="600"
  style="border:0;"
></iframe>
```


🧪 Data Quality Notes

During cleaning, several issues were identified:

~345 trees with coordinates (0,0)

A few unrealistic heights (e.g., 200m)

Some missing street names

Some text-based numeric fields (“6.2” instead of numbers)

Duplicate coordinates due to surveying from the same point

Issues have been documented in GitHub for transparency.

📸 Screenshot

![Annex Tree Map Screenshot](https://github.com/ptoone/annex-tree-map/blob/main/data/annextrees.png?raw=true)

📝 License

This project is open data.
Attribution to the Annex Residents’ Association is appreciated.
