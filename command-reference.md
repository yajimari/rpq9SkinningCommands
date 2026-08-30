# Command Reference

## Contents

- [rpq9CopyBackVertexSkinWeights](#rpq9CopyBackVertexSkinWeights)
- [rpq9CopyBackVertexDeformerWeights](#rpq9CopyBackVertexDeformerWeights)
- [rpq9MirrorSkinWeights](#rpq9MirrorSkinWeights)

---

## rpq9CopyBackVertexSkinWeights

### Overview
rpq9CopyBackVertexSkinWeights is undoable.  
This command copies the skin weights from the back vertices.  
It can only be used with mesh geometry.  
When selecting components, you can use either vertices or faces. Depending on the component type, the normals used to find the back vertices will differ: vertex normals are used for vertex selections, and face normals are used for face selections.

### Flag

| Long                    | Short  | Type     | Description                      |
| ----------------------- | ------ | -------- | -------------------------------- |
| `maxParam`              | `mp`   | `float`  | Maximum distance for back vertex search. The default value is std::numeric_limits<float>::max(). |
| `threshold`             | `t`    | `float`  | Threshold used when findBackVertexMethod is set to raycast. The derault value is 0.001. |
| `findBackVertexMethod`  | `fbvm` | `int`    | This flag controls how back vertices are obtained.: "scoring" or "rayCast". The default is scoring. |
| `skinCluster`           | `sc`   | `string` | Name of the skin cluster used for back vertex copying. By default, the last skin cluster is used. |

---
<br>

## rpq9CopyBackVertexDeformerWeights

### Overview
rpq9CopyBackVertexDeformerWeights is undoable.  
This command copies the deformer weights from the back vertices.  
It can only be used with mesh geometry.  
When selecting components, you can use either vertices or faces. Depending on the component type, the normals used to find the back vertices will differ: vertex normals are used for vertex selections, and face normals are used for face selections.

### Flag

| Long                    | Short  | Type     | Description                      |
| ----------------------- | ------ | -------- | -------------------------------- |
| `maxParam`              | `mp`   | `float`  | Maximum distance for back vertex search. The default value is std::numeric_limits<float>::max(). |
| `threshold`             | `t`    | `float`  | Threshold used when findBackVertexMethod is set to raycast. The derault value is 0.001. |
| `findBackVertexMethod`  | `fbvm` | `uint`   | This flag controls how back vertices are obtained.: "scoring" or "rayCast". The default is scoring. |
| `deformer`              | `d`    | `string` | Name of the deformer used for back vertex copying. |

---
<br>

## rpq9MirrorSkinWeights

### Overview
rpq9MirrorSkinWeights is undoable.  
This command mirrors skin weights.  
It can only be used with mesh geometry.  
Because the mirror operation also uses the skin weights of the vertices on the target side, the skin weights of the vertices on the source side may also be updated.  

### Flag

| Long                    | Short  | Type     | Description                      |
| ----------------------- | ------ | -------- | -------------------------------- |
| `mirrorSource`          | `ms`   | `uint`   | This flag controls the mirror axis using emuns starting from 0.: "x", "y", "z", "-x", "-y" or "-z". The default is "x". |
| `namingConvention`      | `nc`   | [`string`, `string`] | Regular expressions for the names used when classifying influences. Source-side and target-side strings. If not set, the joint label will be used. |
| `threshold`             | `t`    | `float`  | Threshold used when interpolate mirror side weights. The derault value is 1e-10. |
| `skinCluster`           | `sc`   | `string` | Name of the skin cluster used for back vertex copying. By default, the last skin cluster is used. |

---
<br>

## rpq9SkinWeightDisplay

### Overview
rpq9SkinWeightDisplay is NOT undoable.  
This command modify settings of "rpq9 VP2 Skinning Renderer Override".  

### Flag

| Long                    | Short  | Type     | Description                      | Properties |
| ----------------------- | ------ | -------- | -------------------------------- | -----------|
| `skinCluster`           | `sc`   | `string` | skinCluster name of display weights. | C Q   |
| `influence`             | `inf`  | `string` | influence name of display weights. | C Q   |
| `displayColorRamp`      | `dcr`  | `bool`   | Set whether to display the color ramp. | C Q   |
| `displayWeightValues`   | `dwv`  | `bool`  | Set whether to display the weight values. | C Q   |
| `remove`                | `rm`   |  | remove skinCluster from display weights target list. | C   |
| `clear`                 | `cl`   |  | clear display weights target list. | C   |
| `defaultValue` | `dv` |  | In create mode, reset all global settings to their built-in defaults. In query mode, query the built-in default selected by a global setting flag. | C Q |
| `valueRampPoint`        | `vrp`  | [`int`, `float`, `float`, `float`] | Set the color ramp colors, as well as the ramp point indices (0 to 4) and RGB values. | C Q   |
| `valueDecimalPlaces`    | `vdp`  | `uint` | Number of decimal places for displayed skin weight values. | C Q   |
| `valueTextColor`        | `vtc`  | [`float`, `float`, `float`, `float`] | Skin weight values display color. | C Q   |
| `valueFontSize`         | `vfs`  | `uint` | Skin weight values font size. | C Q   |

---
<br>