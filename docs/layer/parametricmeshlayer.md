# ParametricMeshLayer object

`app.project.item(index).layer(index)`

!!! note
    This functionality was added in After Effects 26.3

#### Description

The ParametricMeshLayer object represents a Parametric Mesh layer within a composition.

!!! info
	ParametricMeshLayer is a subclass of [AVLayer object](avlayer.md). All methods and attributes of AVLayer are available when working with ParametricMeshLayer.

#### Example

If the first item in the project is a CompItem, and the first layer of that CompItem is a ParametricMeshLayer, the following checks its type.

```javascript
var layer = app.project.item(1).layer(1);
if (layer instanceof ParametricMeshLayer)
{
    // do something
}
```

## Attributes

### ParametricMeshLayer.meshType

`app.project.item(index).layer(index).meshType`

#### Description

For a parametric mesh layer, its mesh type. Trying to set this attribute for a non-parametric mesh layer produces an error.

#### Type

A `MeshType` enumerated value; read/write. One of:

- `MeshType.SPHERE`
- `MeshType.PLANE`
- `MeshType.CYLINDER`
- `MeshType.CONE`
- `MeshType.TORUS`
- `MeshType.CUBE`

---

### ParametricMeshLayer.MeshOptions

`comp.layer(index).meshOptions`

#### Description

Gets/sets details about the structure of the parametric mesh.

#### Type

`MeshOptions` based on the MeshType of the layer, as follows.

#### For MeshType.CUBE
- `MeshOptions.width`
- `MeshOptions.height`
- `MeshOptions.depth`
- `MeshOptions.smoothingAngle`

#### For MeshType.SPHERE
- `MeshOptions.radius`
- `MeshOptions.sides`
- `MeshOptions.sliceCaps`
- `MeshOptions.sliceStart`
- `MeshOptions.sliceEnd`
- `MeshOptions.smoothingAngle`

#### For MeshType.PLANE
- `MeshOptions.width`
- `MeshOptions.length`
- `MeshOptions.cornerRadius`
- `MeshOptions.cornerSides`

####  For Meshtype.TORUS
- `MeshOptions.ringRadius`
- `MeshOptions.pipeRadius`
- `MeshOptions.ringSides`
- `MeshOptions.pipeSides`
- `MeshOptions.caps`
- `MeshOptions.sliceStart`
- `MeshOptions.sliceEnd`
- `MeshOptions.smoothingAngle`

####  For MeshType.CONE
- `MeshOptions.topRadius`
- `MeshOptions.bottomRadius`
- `MeshOptions.height`
- `MeshOptions.sides`
- `MeshOptions.topCap`
- `MeshOptions.bottomCap`
- `MeshOptions.sliceCaps`
- `MeshOptions.sliceStart`
- `MeshOptions.sliceEnd`
- `MeshOptions.smoothingAngle`

#### For MeshType.CYLINDER
- `MeshOptions.radius`
- `MeshOptions.height`
- `MeshOptions.sides`
- `MeshOptions.topCap`
- `MeshOptions.bottomCap`
- `MeshOptions.sliceCaps`
- `MeshOptions.sliceStart`
- `MeshOptions.sliceEnd`
- `MeshOptions.smoothingAngle`

---

#### ParametricMeshLayer.BevelOptions

`comp.layer(index).bevelOptions`

#### Description

Gets/sets details about the beveling of the parametric mesh.

!!! info
	Only Parametric Mesh Layers with `MeshType.CUBE`, `MeshType.CONE`, and `MeshType.CYLINDER` have `BevelOptions`.

#### Type

`BevelOptions` based on the MeshType of the layer, as follows.


#### For MeshType.CUBE
- `bevelOptions.radius`
- `bevelOptions.sides`

#### For MeshType.CONE
- `bevelOptions.topRadius`
- `bevelOptions.topSides`
- `bevelOptions.bottomRadius`
- `bevelOptions.bottomSides`

#### For MeshType.CYLINDER
- `bevelOptions.radius`
- `bevelOptions.sides`

---

