For this project I wanted to find out what possibilities there are for seeing how quick I can reach something from a certain location. 
## Path between points
First step was to write something to see if I could visualize a simple route between some points, based on the order given and the coordinates of the points. I wanted to use OSM as a map provider and as a router Graphhopper, since OSM is open source and Graphhopper since it provides enough free requests for my needs. To keep the routing simple for now, I will only consider cars in this phase, and no traffic. 
```python
client = Graphhopper(api_key=api_key)
route = client.directions(locations=coords, profile='car')
```
To generate the map I will use folium, since it provides a nice format and plenty of render possibilities like a zoomable html. A challenge I encountered in this phase is that the coordinates as I put them into the Graphhopper API and the plot in folium are reversed. That means that in one of them the coordinates of Berlin are `[13.413706, 52.490202]` and in the other are `[52.490202, 13.413706]`. To accommodate this difference I made a simple function to reverse them. 


Tree map of project this phase
