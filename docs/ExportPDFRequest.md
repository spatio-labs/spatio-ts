
# ExportPDFRequest

Optional body for `POST /v1/slides/{id}/export/pdf`. Renderer posts pre-rasterized PNGs for slides that contain Fabric.js elements (the sidecar can\'t run Fabric server-side); slides without an entry are rendered from their `layout` + theme. 

## Properties

Name | Type
------------ | -------------
`rasterizedSlides` | [Array&lt;ExportPDFRequestRasterizedSlidesInner&gt;](ExportPDFRequestRasterizedSlidesInner.md)
`theme` | { [key: string]: any; }

## Example

```typescript
import type { ExportPDFRequest } from '@spatio-labs/spatio-ts'

// TODO: Update the object below with actual values
const example = {
  "rasterizedSlides": null,
  "theme": null,
} satisfies ExportPDFRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExportPDFRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


