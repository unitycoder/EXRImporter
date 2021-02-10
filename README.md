# EXRImporter
EXR importer for Unity Editor.

Currently only Windows platform is supported.

This package includes following native libraries.

- https://github.com/takazerker/EXRImporter
- https://github.com/AcademySoftwareFoundation/openexr

# Example

```cs
using (var exr = new EXRImporter.EXRFile(PathToEXRFile))
{
    Texture2D temp = new Texture2D(file.width, file.height, TextureFormat.RGBAFloat, false);
    var pixels = temp.GetRawTextureData<Color>();
    exr.CopyRGBAData(pixels);
    File.WriteAllBytes("test.exr", temp.EncodeToEXR());
    DestroyImmediate(temp);
}
```
