# SourceStage — SFM Model Importer & Face Poser

SourceStage is a Blender add-on for importing and preparing Source Engine characters for posing and animation. It works with [SourceIO](https://github.com/REDxEYE/SourceIO) and supports SFM-style rigs, Rigify rigs, facial controls, and collection-based outfit and prop switches.

## Features

- Browse and import Source Engine models through SourceIO.
- Keep the original SFM skeleton or create a Rigify control rig.
- Prepare facial shape keys and Source HWM flex controls for animation.
- Control paired facial expressions independently on the left and right sides.
- Add an eye target and create a replacement eye material.
- Create a `Groups to Bone` controller with visibility switches for detected model collections.
- Manually switch collection variants or attach a collection of clothing and accessories to a selected bone.

## Requirements

- Blender 5.2 or newer.
- SourceIO installed and enabled for Source Engine model import.
- Rigify enabled when you want to generate a Rigify rig.

## Installation

1. Download `sfm_importer_faceposer.zip` from the project's Releases or repository files.
2. In Blender, open **Edit → Preferences → Add-ons**.
3. Choose **Install from Disk** and select the ZIP file.
4. Enable **SourceStage — SFM Model Importer & Face Poser**.
5. Open the 3D View sidebar with **N**, then choose the **SFM Import** tab.

Keep the add-on folder structure intact when installing manually. The main `__init__.py` file needs the `sfm_importer_faceposer_parts` folder beside it.

## Quick start

1. In **Model Importer**, choose a model folder, press **Scan Folder**, select a model, and import it.
2. Choose the SFM skeleton or the generated Rigify rig in **Clothing & Items**.
3. Press **Groups to Bone** to add a `CTRL_Groups` bone above the character and create visibility properties for the detected collections. The properties are available on that pose bone.
4. For manual setup, choose a collection and select **Replace variants** or **Attach to bone**, then press the corresponding action button.
5. Select the face mesh and open **Face Poser** to prepare and animate facial controls.

## Collection controls

**Groups to Bone** creates one visibility property for each detected model collection. Set a property's value to show or hide that collection. For mutually exclusive outfit variants, use **Replace variants** on a collection whose child collections represent the available states.

Use **Attach to bone** to parent accessories such as hats, gloves, or boots to a bone. Meshes with vertex groups keep their weights and use an armature modifier when attached; objects without weights are attached rigidly to the selected bone.

## Notes

- Collection switches depend on the model's collection hierarchy and armature relationships. Review the detected groups before animating.
- The replacement eye shader is a Blender approximation intended to keep the iris stable relative to the eye target; it is not a byte-for-byte recreation of Source's native shader.
- Save a copy of your `.blend` file before applying large-scale changes to imported models.

## License

Add the license that applies to this project before publishing or distributing it. Check the licenses of bundled code, SourceIO, and any included assets separately.
