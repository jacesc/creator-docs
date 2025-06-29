---
title: 3D Importer
description: 3D Importer imports third-party .fbx, .gltf, and .obj 3D model assets into Studio.
---

<iframe width="800" height="450" src="https://www.youtube-nocookie.com/embed/4RonlfpKzHA" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br />

The 3D Importer allows you to import `.fbx`, `.gltf`, or `.obj` 3D models into Studio as a custom `Class.Model`.

- Meshes with basic or PBR ([surface appearance](../../art/modeling/surface-appearance.md)) textures.
- Meshes with [rigging and skinning data](../../art/modeling/rigging.md).
- Meshes with animation data.
- Specialized meshes, such as [accessories](../../art/accessories/index.md), or characters with [facial animation data](../../art/characters/facial-animation/index.md).

<BaseAccordion>
<AccordionSummary>
<Typography variant="subtitle2">Supported file type features</Typography>
</AccordionSummary>
<AccordionDetails>
<table><thead>
  <tr>
    <th style={{width:"20%"}}>**File type**</th>
    <th style={{width:"40%"}}>**Studio compatibility**</th>
    <th>**Best for**</th>
  </tr></thead>
<tbody>
  <tr>
    <td>OBJ (`.obj`)</td>
    <td>Supports:<br/><br/>— Basic single mesh objects</td>
    <td>Simple mesh geometry use-cases.</td>
  </tr>
  <tr>
    <td>FBX (`.fbx`)</td>
    <td>Supports:<br/><br/>— Multiple mesh objects and hierarchies<br/>—  Textures, including basic and [PBR textures](../../art/modeling/surface-appearance.md).<br/>— Cage mesh objects<br/>— [Rigging and armature data](../../art/modeling/rigging.md)<br/>— Additional components for [avatar](../../avatar/index.md) items.<br/>— Animation data<br/>— [Vertex colors](../blender.md#vertex-painting)</td>
    <td>Any type of 3D import, including but not limited to [game assets](../../assets.md) or [avatar items](../../avatar).</td>
  </tr>
  <tr>
    <td>gLTF (`.gltf`)</td>
    <td>Supports:<br/><br/>— Multiple mesh objects and hierarchies<br/>— Textures, including basic and [PBR textures](../../art/modeling/surface-appearance.md).<br/>— Cage mesh objects<br/>— [Rigging and armature data](../../art/modeling/rigging.md)<br/>— Additional components for [avatar](../../avatar/index.md) items.<br/>— Animation data<br/>— [Vertex colors](../blender.md#vertex-painting)</td>
    <td>Any type of 3D import, including but not limited to [game assets](../../assets.md) or [avatar items](../../avatar).</td>
  </tr>
</tbody></table>
</AccordionDetails>
</BaseAccordion>

<Alert severity ='info'>
To directly import 3D assets using HTTP requests, see the [Open Cloud usage guide for assets](../../cloud/guides/usage-assets.md).
</Alert>

The 3D Importer is divided into three sections:

<img src="../../assets/modeling/meshes/3d-Importer-Panels.png" width="80%" alt="The 3D importer interface, showing a preview of the mesh in the top left, a list of 3D objects on the bottom left, and a list of toggle-able properties on the right side."/>

A. The **preview panel**, located in the top left, allows you to rotate and examine 3D objects before importing into your workspace or Toolbox.

B. The **hierarchy panel**, located in the bottom left, allows you to select specific parts of your model to import or apply specific settings to, including textures, child objects, animations, or rig data.

C. The **inspector panel**, located on the right, allows you to apply various settings to the imported object.

## Import 3D objects

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/ikYZloBgqtE" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br />

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/RCsYZe3LoDM" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br />

Before importing a 3D object, ensure that the `.fbx`, `.gltf` or `.obj` meets Studio's [mesh requirements](../../art/characters/specifications.md) to reduce errors or unexpected behavior.

To import a 3D object:

1. In the toolbar's **Home** or **Avatar** tab, click **Import 3D**. A file browser displays.
2. Select the `.fbx`, `.gltf` or `.obj` you intend to import. The Importer window displays.
3. Verify the object preview and check that the [import settings](#import-settings) are correct for your object.
4. Verify any [warning or error messages](#warnings-and-errors).
5. Click **Import**.

### Import settings

Depending on the object selected in the hierarchy panel, the inspector panel displays the following groups of settings:

- **File General**: Affects the entire imported file.
- **Rig General**: Affects the selected mesh object if rigging data is present.
- **File Transform**: Affects the transform properties of the imported file.
- **File Geometry**: Affects the geometry properties of the imported file.
- **Object General**: Affects the selected child object.
- **Object Geometry**: Affects the geometry of the selected child object.

#### File general

The 3D Importer provides the following settings for all meshes:

<table>
<thead>
  <tr>
    <th>Setting</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Name</td>
    <td>Sets the name of the imported asset as it will appear in your project.</td>
  </tr>
  <tr>
    <td>Import Only As Model</td>
    <td>If enabled, the 3D Importer imports the model as a single asset even if the model contains multiple children. By default, this is **enabled**. <br /><br />If disabled, the 3D Importer imports the model and all descendants, such as the multiple meshes, as individual assets.</td>
  </tr>
  <tr>
    <td>Add Model To Inventory</td>
    <td>If enabled, the 3D Importer adds the model to your **Toolbox** and **Asset Manager** inventory as a new asset. By default, this is **enabled**. <br /><br />If disabled, the 3D Importer does not add the asset to your inventory.</td>
  </tr>
  <tr>
    <td>Insert In Workspace</td>
    <td>If enabled, the 3D Importer inserts the model into the `Class.Workspace` as well as your **Toolbox** and **Asset Manager** inventory. If importing from a saved or published experience, this setting also grants permission to the experience to use the restricted asset. By default, this is **enabled**. <br /><br />If disabled, this setting only adds the model to your inventory and does **not** grant the experience permission to use the asset.</td>
  </tr>
  <tr>
    <td>Insert Using Scene Position</td>
    <td>If enabled, the 3D Importer uses the current scene position when inserting the model into the workspace. By default, this is **disabled**.</td>
  </tr>
  <tr>
    <td>Set Pivot to Scene Origin</td>
    <td>If enabled, the 3D Importer sets the pivot point of the entire model to the scene origin. By default, this is **enabled**.</td>
  </tr>
  <tr>
    <td>Anchored</td>
    <td>If enabled, the 3D Importer sets the Anchored property to True on all the imported MeshParts. This is disabled for meshes with rig data / avatars. By default, this is **disabled**.</td>
  </tr>
  <tr>
    <td>Uses Cage</td>
    <td>If enabled, the 3D Importer finds cage meshes in the model and converts them to `WrapInstance` objects, such as `Class.WrapLayer` or `Class.WrapTarget`. If disabled, the Importer treats them as regular meshes. If the 3D Importer initially detects cage meshes in the model, this is **enabled** by default.</td>
  </tr>
</tbody>
</table>

#### Rig general

The 3D Importer provides the following settings for meshes with rigging data, typically character bodies or clothing accessories:

<table>
<thead>
  <tr>
    <th>Setting</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Rig Type</td>
    <td>Sets the type of rig the mesh should be associated with. The options are:<br />- **R15**<br />- **Custom**<br />- **No Rig**<br /><br />By default, the 3D importer attempts to select the most appropriate setting based on the detected rigging and skinning data of the mesh. </td>
  </tr>
  <tr>
    <td>Validate UGC Body</td>
    <td>After importing, Studio opens the assets in the [Avatar Setup](../../avatar-setup/index.md) tool, allowing you to quickly begin testing and uploading avatar assets to the Marketplace.</td>
  </tr>
  <tr>
    <td>Rig Scale</td>
    <td>If Rig Type is set to R15, the importer provides additional options to specify [body type scaling](../../art/characters/specifications.md#body-scale). The options are:<br />- **Default**<br />- **Rthro**<br />- **Rthro Narrow**</td>
  </tr>
</tbody>
</table>

#### File transform

The 3D Importer provides the following settings for all meshes:

<table>
<thead>
  <tr>
    <th>Setting</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>World Forward</td>
    <td>Sets the forward facing axis of the object. By default, this is set to **Front**.</td>
  </tr>
  <tr>
    <td>World Up</td>
    <td>Sets the upward facing axis of the object. By default, this is set to **Top**.</td>
  </tr>
</tbody>
</table>

#### File geometry

File geometry includes information on the file dimensions and polycount of the entire model. You can edit the following settings for all meshes:

<table>
<thead>
  <tr>
    <th>Setting</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Scale Unit</td>
    <td>Sets what units the file was modeled in so that it's sized appropriately when imported. By default, this is set to **Studs**.</td>
  </tr>
  <tr>
    <td>Merge Meshes</td>
    <td>If enabled, merges all MeshParts in the model into a single MeshPart and creates one MeshPart rather than a Model. By default, this is **disabled**.</td>
  </tr>
  <tr>
    <td>Invert Negative Faces</td>
    <td>Inverts the orientation of negative faces in the mesh. By default, this is **disabled**.</td>
  </tr>
</tbody>
</table>

#### Object general

When selecting a specific child object of your mesh, the 3D Importer populates Object General settings. You can edit the following settings for the selected child objects:

<table>
<thead>
  <tr>
    <th>Setting</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Name</td>
    <td>Sets the name of the selected child object within the model.</td>
  </tr>
  <tr>
    <td>Anchored</td>
    <td>If enabled, sets the Anchored property to True on the selected child object. By default, this is **disabled**.</td>
  </tr>
  <tr>
    <td>Use Imported Pivot</td>
    <td>If enabled, imports the object using the pivot point set within the child object. By default, this is **enabled**.</td>
  </tr>
</tbody>
</table>

#### Object geometry

Object Geometry includes information on the dimensions and polycount of the selected child object of the model. You can edit the following settings for the selected child objects:

<table>
<thead>
  <tr>
    <th>Setting</th>
    <th>Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Make Double Sided</td>
    <td>If disabled, sets the vertices as one-sided. One-sided vertices means that you can see through them from one side. <br /><br />If enabled, sets the vertices as double-sided. Vertices that are double sided visually render on both sides. Double-sided is more performance intensive.<br /><br />By default, this is **disabled**. </td>
  </tr>
  <tr>
    <td>Ignore Vertex Colors</td>
    <td>If enabled, ignores the vertex color data in the child object. By default, this is **disabled**. </td>
  </tr>
</tbody>
</table>

### Warnings and errors

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/UEHEsmCslBU" title="YouTube video player" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br />

If Studio detects any issues with your model, a small indicator displays in the hierarchy panel or the settings panel.

If you see a warning icon in the hierarchy, expand the hierarchy until you reach the specific child object to see more information about the issue. Warning and error messages display in the settings panel or as a tooltip.

<GridContainer numColumns="2">
  <figure>
    <img src="../../assets/modeling/meshes/Warning-Settings-Panel.png" alt="A warning message in orange stating an error about cages mismatching."/>
    <figcaption>Warning and error messages display in the appropriate section in the inspector panel.</figcaption>
  </figure>
  <figure>
    <img src="../../assets/modeling/meshes/Warning-Mouse-Over.png" alt="An error message in red with a pop-up message about missing textures."/>
    <figcaption>Some errors display a tooltip when hovering over the error icon.</figcaption>
  </figure>
</GridContainer>
