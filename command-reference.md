# Command Reference

## Contents

- [rpq9CopyBackVertexSkinWeights](#rpq9CopyBackVertexSkinWeights)
- [rpq9CopyBackVertexDeformerWeights](#rpq9CopyBackVertexDeformerWeights)

---

## rpq9CopyBackVertexSkinWeights

### Overview
rpq9CopyBackVertexSkinWeights is undoable.  
This command copies the skin weights from the back vertices.  
It can only be used with mesh geometry.  
When selecting components, you can use either vertices or faces. Depending on the component type, the normals used to find the back vertices will differ: vertex normals are used for vertex selections, and face normals are used for face selections.

### Flag

| Long                    | Short  | Type | Description                      |
| ----------------------- | ------ | -------- | -------------------------------- |
| `maxParam`              | `mp`   | `float`  | Maximum distance for back vertex search. The default value is std::numeric_limits<float>::max(). |
| `threshold`             | `t`    | `float`  | Threshold used when findBackVertexMethod is set to raycast. The derault value is 0.001. |
| `findBackVertexMethod`  | `fbvm` | `int`    | This flag controls how back vertices are obtained.: "score" or "rayCast". The default is default. |
| `skinCluster`           | `sc`   | `string`  | Name of the skin cluster used for back vertex copying. By default, the last skin cluster is used. |

---
<br>

## rpq9CopyBackVertexDeformerWeights

### Overview
rpq9CopyBackVertexDeformerWeights is undoable.  
This command copies the deformer weights from the back vertices.  
It can only be used with mesh geometry.  
When selecting components, you can use either vertices or faces. Depending on the component type, the normals used to find the back vertices will differ: vertex normals are used for vertex selections, and face normals are used for face selections.

### Flag

| Long                    | Short  | Type | Description                      |
| ----------------------- | ------ | -------- | -------------------------------- |
| `maxParam`              | `mp`   | `float`  | Maximum distance for back vertex search. The default value is std::numeric_limits<float>::max(). |
| `threshold`             | `t`    | `float`  | Threshold used when findBackVertexMethod is set to raycast. The derault value is 0.001. |
| `findBackVertexMethod`  | `fbvm` | `int`    | This flag controls how back vertices are obtained.: "score" or "rayCast". The default is default. |
| `deformer`              | `d`    | `string`  | Name of the deformer used for back vertex copying. |
