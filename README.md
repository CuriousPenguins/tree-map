🌳 Community Tree MapA lightweight, open-source platform for mapping urban forests.Live Demo: treemap.xyz.am | Community Example: The Annex Tree Map📍 OverviewCommunity Tree Map is a turnkey solution for neighbourhoods, campus groups, and conservationists to visualize and catalog trees.Unlike complex GIS systems, this project runs on Flat Data. It requires no database server (SQL) and hosts entirely for free on platforms like GitHub Pages (static mode) or standard shared hosting (PHP mode).Use this template to:Visualize thousands of trees on an interactive map.Crowdsource data corrections from residents (no login required).Monitor tree health, species diversity, and size (DBH).Publish open data for students and researchers.🚀 Live Demo & ExamplesWe run a live instance for the Annex Neighbourhood in Toronto, showcasing historical data collected by volunteers between 2010–2014.SiteURLDescriptionMain Projecttreemap.xyz.amThe main template and landing page.Annex Mapannextrees.xyz.amA fully populated example with ~1,200 trees.Data Toolscoordinates.xyz.amHelper tool for grabbing lat/lng coordinates.✨ Key Features🗺️ Interactive Map: Built with Leaflet.js and OpenStreetMap. Fast, mobile-friendly, and capable of handling 5,000+ points.📂 Flat Data Architecture: All data lives in a single data.json file. No MySQL or PostgreSQL required.✏️ Community Editing: Includes a Suggest an Edit form that allows residents to submit corrections (species, height, status) without needing a GitHub account.🛡️ Automated Workflows: User submissions automatically create formatted GitHub Issues for maintainers to review.📊 Automatic Stats: Dashboard automatically calculates total trees, most common species, and update frequency.🛠️ Quick Start (Create Your Own Map)Want to map your own neighbourhood?Fork this RepositoryClick the "Fork" button on GitHub to create your own copy.Add Your DataReplace data/trees.json with your own GeoJSON data. (See Data Structure below).ConfigureRename config.sample.php to config.php and update your settings:PHPreturn [
    'site_name' => 'My Neighbourhood Tree Map',
    'center_lat' => 43.6532,
    'center_lng' => -79.3832,
    // ...
];
DeployUpload files to any PHP-enabled web host (cPanel, Apache, Nginx) or run locally.🌲 Data StructureThe system uses standard GeoJSON. You can generate this using QGIS, Python, or our built-in JSON generator tool.File Location: /data/trees.jsonJSON{
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
        "DBH": "28.0",           // Diameter at Breast Height (cm)
        "total_height": "8.5",   // Height (m)
        "date_surveyed": "2024-05-12",
        "condition": "Good"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [ -79.405501, 43.673770 ] // [Lng, Lat]
      }
    }
  ]
}
🧰 Adding New TreesDon't like writing JSON by hand?Visit treemap.xyz.am/contribute.php to use the built-in generator form.🤝 Contributing & CommunityWe welcome contributions to the code or the dataset!For Developers (Code)Frontend: Bootstrap 5, Leaflet JS.Backend: PHP 7.4+ (Strict Types).To Do: We are looking for help improving the mobile filter UI and adding a dark mode for the map.For Arborists/Volunteers (Data)If you see an error in the live map:Click the "Suggest an Edit" button on the website.Fill out the form (Tree #, correct species, or new measurements).This will generate a GitHub Issue for our maintainers to review.🔗 EmbeddingYou can embed the tree map on your community association or BIA website using an iframe:HTML<iframe
  src="https://treemap.xyz.am/map.php"
  width="100%"
  height="600"
  style="border:0; border-radius: 8px;"
  loading="lazy"
></iframe>
📝 License & CreditsCode: MIT License. Free to use and modify.Data (Annex Demo): Sourced from the Annex Residents’ Association (ARA) volunteers (2010–2014).Map Tiles: © OpenStreetMap contributors.
