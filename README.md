# 🌳 Community Tree Map

**A lightweight, open-source platform for mapping urban forests.**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
![PHP](https://img.shields.io/badge/PHP-7.4%2B-blue)
![Leaflet](https://img.shields.io/badge/Leaflet-1.9-green)
![Data](https://img.shields.io/badge/Data-Open%20GeoJSON-orange)

## 📍 Overview

**Community Tree Map** is a turnkey solution for neighbourhoods, campus groups, and conservationists to visualize and catalog trees.

Unlike complex GIS systems, this project runs on **Flat Data**. It requires no database server (SQL) and hosts entirely for free on platforms like GitHub Pages (static mode) or standard shared hosting (PHP mode).

**Use this template to:**
* Visualize thousands of trees on an interactive map.
* Crowdsource data corrections from residents (no login required).
* Monitor tree health, species diversity, and size (DBH).
* Publish open data for students and researchers.

---

## 🌐 Live Demos

We run a main template site for general use, and a specific live instance for the **Annex Neighbourhood** in Toronto (showcasing historical data collected by volunteers).

| Site | URL | Description |
| :--- | :--- | :--- |
| **Main Template** | [treemap.xyz.am](https://treemap.xyz.am) | The generic project landing page and template. |
| **Live Example (Annex)** | [annextreemap.xyz.am](https://annextreemap.xyz.am) | A fully populated map with ~1,200 trees. |
| **Project Docs** | [annextrees.xyz.am](https://annextrees.xyz.am) | Documentation and context for the Annex project. |
| **Helper Tool** | [coordinates.xyz.am](https://coordinates.xyz.am) | Utility for grabbing lat/lng coordinates. |

---

## ✨ Key Features

* **🗺️ Interactive Map:** Built with [Leaflet.js](https://leafletjs.com/) and OpenStreetMap. Fast, mobile-friendly, and capable of handling 5,000+ points.
* **📂 Flat Data Architecture:** All data lives in a single `data.json` file. No MySQL or PostgreSQL required.
* **✏️ Community Editing:** Includes a `Suggest an Edit` form that allows residents to submit corrections (species, height, status) without needing a GitHub account.
* **🛡️ Automated Workflows:** User submissions automatically create formatted GitHub Issues for maintainers to review.
* **📊 Automatic Stats:** Dashboard automatically calculates total trees, most common species, and update frequency.

---

## 🛠️ Quick Start (Create Your Own Map)

Want to map your own neighbourhood?

1.  **Fork this Repository**
    Click the "Fork" button on GitHub to create your own copy.

2.  **Add Your Data**
    Replace `data/trees.json` with your own GeoJSON data. (See *Data Structure* below).

3.  **Configure**
    Rename `includes/config.sample.php` to `config.php` (if using PHP backend) and update your settings:
    ```php
    return [
        'site_name' => 'My Neighbourhood Tree Map',
        'center_lat' => 43.6532,
        'center_lng' => -79.3832,
        // ...
    ];
    ```

4.  **Deploy**
    Upload files to any PHP-enabled web host (cPanel, Apache, Nginx) or run locally.

---

## 🌲 Data Structure

The system uses standard **GeoJSON**. You can generate this using QGIS, Python, or our built-in JSON generator tool.

**File Location:** `/data/annex-trees.json` (or `trees.json`)

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "tree_no": "104",
        "species_code": "acrsac",
        "tree_name": "Sugar Maple",
        "house_number": "42",
        "street_code": "Kendal Ave",
        "DBH": "28.0",           
        "total_height": "8.5",   
        "date_surveyed": "2024-05-12",
        "condition": "Good"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [ -79.405501, 43.673770 ] 
      }
    }
  ]
}
   ```

### 🧰 Adding New Trees
Don't like writing JSON by hand?
Visit the **Contribute** page on your deployment to use the built-in generator form.

---

### 🤝 Contributing
We welcome contributions to the code or the dataset!

#### For Developers (Code)
* **Frontend:** Bootstrap 5, Leaflet JS.
* **Backend:** PHP 7.4+ (Strict Types).
* **To Do:** We are looking for help improving the mobile filter UI and adding a dark mode for the map.

#### For Arborists/Volunteers (Data)
If you see an error in the live map:
1. Click the **"Suggest an Edit"** button on the website.
2. Fill out the form (Tree #, correct species, or new measurements).
3. This will generate a GitHub Issue for our maintainers to review.

---

### 🔗 Embedding
You can embed the tree map on your community association or BIA website using an iframe:

```html
<iframe
  src="[https://annextreemap.xyz.am/](https://annextreemap.xyz.am/)"
  width="100%"
  height="600"
  style="border:0; border-radius: 8px;"
  loading="lazy"
></iframe>
