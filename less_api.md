---
title: Less API
permalink: /less-api/
---

Item                                           | Description
-----------------------------------------------|-------------------------
`@su-assetpath`                                | Theme asset folder path. Ex.: `background:url('@{su-assetpath}/image.png');`
`.theme-image-fit(@which; @width; @height;)`   | Path to image resized to fit within provided dimensions.
`.theme-image-fill(@which; @width; @height;)`  | Path to image cropped to fill provided dimensions. Won't crop small images.
`.theme-image-ratio(@which; @width; @height;)` | Path to image cropped to match provided ratio. Will crop small images.
