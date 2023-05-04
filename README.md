# stix

[![GitHub release](https://img.shields.io/github/release/go-fonts/stix.svg)](https://github.com/go-fonts/stix/releases)
[![GoDoc](https://godoc.org/github.com/go-fonts/stix?status.svg)](https://godoc.org/github.com/go-fonts/stix)
[![License](https://img.shields.io/badge/License-BSD--3-blue.svg)](https://github.com/go-fonts/stix/raw/main/LICENSE)

`stix` provides the [STIX](https://www.stixfonts.org/) fonts as importable Go packages.

The fonts are released under the [SIL Open Font](https://github.com/go-fonts/stix/raw/main/SIL-LICENSE) license.
The Go packages under the [BSD-3](https://github.com/go-fonts/stix/raw/main/LICENSE) license.

## Example

```go
import (
	"fmt"
	"log"

	"github.com/go-fonts/stix/stix2math"
	"golang.org/x/image/font/sfnt"
)

func Example() {
	ttf, err := sfnt.Parse(stix2mathregular.TTF)
	if err != nil {
		log.Fatalf("could not parse STIX2 Math font: %+v", err)
	}

	var buf sfnt.Buffer
	v, err := ttf.Name(&buf, sfnt.NameIDVersion)
	if err != nil {
		log.Fatalf("could not retrieve font version: %+v", err)
	}

	fmt.Printf("version:    %s\n", v)
	fmt.Printf("num glyphs: %d\n", ttf.NumGlyphs())

	// Output:
	// version:    Version 2.13 b171
	// num glyphs: 6760
}
```
