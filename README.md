# Treefolio Recommendation System

## TBD

The important part for you to know is instructions on how to put things in the boro format.

First off, load the boroboundaries.geojson in QGIS. This will give you a visual representation of the boundaries of the boro.

Next, load in any NY dataset you want. Trees, parks, schools, churches, streets, etc.

Now, we want to go to Processing - Toolbox - Join attributes by location. This will allow you to join the boro boundaries with the dataset you loaded in. This will give you a new dataset with the boro name as an attribute.

INPUT: NY dataset
JOIN: boro boundaries
FIELDS: boro_CD

Make SURE to get that boro_cd field! This is the field that will have the boro name.

Now, this will make a new layer with the dataset annotated with a field that has its boro name.

Now, we want to go to Processing - Toolbox - Split vector layer. This will allow you to split the dataset into separate layers based on the boro name.

INPUT: NY dataset with boro name
FIELD: boro_cd
DIRECTORY: where you want to save the new files (make an empty folder for this)

This will make a new seperated geojson or other spatial format file for each boro, saved to your directory of choice.

TBD- This will export large (2gb+) files for some boros that are just gigantic, think Staten Island.
In the future, might want to use an MBTiles server or somehow segment+load larger files. Like, part001.geojson, part002.geojson, etc.

As we can't upload >100mb files to Github.