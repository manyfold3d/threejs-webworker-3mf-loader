# THREE.js 3MF Loader for Web Workers

The standard THREE.js 3MF loader [cannot be used](https://github.com/mrdoob/three.js/issues/18838) in a Web Worker, as it uses DOMParser.

This tiny fork includes the normal loader code and patches it with the [xmldom](https://www.npmjs.com/package/xmldom) and [query-selector](https://www.npmjs.com/package/query-selector) packages, as suggested in [this GitHub comment](https://github.com/xmldom/xmldom/issues/92#issuecomment-718091535).

This makes the loader usable in a Web Worker.

## Installation

`npm install https://github.com/manyfold3d/threejs-webworker-3mf-loader`

or

`yarn add https://github.com/manyfold3d/threejs-webworker-3mf-loader`

## Usage

```
import { ThreeMFLoader } from 'threejs-webworker-3mf-loader'

loader = new ThreeMFLoader()
model = loader.load(path)
```

## Maintenance

This code will be updated occasionally with the 3MF loader code from upstream THREE.js, but I can't guarantee I'll notice. Feel free to open issues to remind me if it changes.

## Credits

All credit goes to the three.js authors for all their work, and @coder-free and @morrisallison for their suggestions in various GitHub comments, which I've just wrapped up into this package.
