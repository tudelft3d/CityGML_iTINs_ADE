# CityGML_iTINs_ADE

CityGML extension for modelling massive TIN terrains

# Details

Terrains form an important part of 3D city models. In CityGML, terrains are defined within the thematic module Relief. We are interested in the TIN representation of terrains. With advancements in 3D data acquisition and processing technologies, it is now possible to generate billions of 3D points for simply an area of few square kilometers and therefore, the TIN generated from these points is also massive in size. The main problem with such voluminous is how to efficiently store and maintain them? 

While the international 3D GIS standard CityGML supports the storage of TINs, the current representation is not adequate and has limitations. Firstly, the CityGML datasets can become very large in size because of the redundancy in the underlying data structure. Furthermore, it does not store the topological relationships of the triangles. Therefore, we focus on an improved storage representation for massive terrain models as TINs in the context of 3D city models. We reviewed different data structures for compactly representing TINs, and explored how they can be implemented in CityGML to efficiently store massive terrains. 

Three existing compact TIN data structures, namely Indexed triangles, TriStrips, and Stars are introduced as new geometry types in GML geometry model for representing TINs. These new geometry types are extended to CityGML as an ADE (Application Domain Extension) for compactly representing massive TIN terrains.

Our approach allows to explicitly store the topological relationships of a TIN model. Experiments with massive real-world terrains show that it enables to compress up to a factor of ∼29 with 1 billion+ triangles.

# XML Schemas

We introduced new geometry types (primitives, aggregates and composites) in this model for compactly representing TINs which are defined in a separate XSD file "iTIN GML.xsd" with a different namespace ["http://godzilla.bk.tudelft.nl/schemas/iTIN_GML"](http://godzilla.bk.tudelft.nl/schemas/iTIN_GML) and the "igml" identifier".

For modelling terrains as TINs, these "iTIN GML" elements are added to CityGML as an ADE. The ADE classes are defined in a separate file "CityGML iTINs ADE.xsd" with a different namespace ["http://godzilla.bk.tudelft.nl/schemas/iTINs_ADE"](http://godzilla.bk.tudelft.nl/schemas/iTINs_ADE) and the "itin" identifier.

# Resources

The **UML model** of the iTIN_GML and CityGML_iTINs_ADE was created using Enterprise Architect.  
- This [Enterprise Architect file](https://github.com/tudelft3d/CityGML_iTINs_ADE/blob/master/UML/CityGML_iTINs_ADE_0_1.eap) contains the UML model.
- The UML diagrams can be downloaded in [PDF format](https://github.com/tudelft3d/CityGML_iTINs_ADE/blob/master/Documentation/UMLDiagrams.pdf) as well.

The **XML Schema files** of the iTIN_GML and CityGML_iTINs_ADE were derived automatically from the UML model using ShapeChange(http://shapechange.net/).  
- This is the derived [XML Schema file](https://github.com/tudelft3d/CityGML_iTINs_ADE/blob/master/XSD/iTINGML.xsd) for iTIN_GML.
- This is the derived [XML Schema file](https://github.com/tudelft3d/CityGML_iTINs_ADE/blob/master/XSD/CityGML_iTINs_ADE.xsd) for CityGML_iTINs_ADE.
- Browsable schema for the ADE can be accessed [here](https://github.com/tudelft3d/CityGML_iTINs_ADE/blob/master/Documentation/BrowsableSchema/index.html). 

# More information

[OGC CityGML](http://www.opengeospatial.org/standards/citygml) is an XML based data model for the storage and exchange of virtual 3D city models. It is implemented an application schema of GML3 [Geography Markup Language version 3.1.1 (GML3)](http://www.opengeospatial.org/standards/gml). The data model of CityGML comprises of a core module and several thematic extension modules like Building, Relief, Bridge, LandUse, Tunnel, Transportation, Vegetation, WaterBody, etc for representing 3D city models. For more information, visit [citygml.org](www.citygml.org).
