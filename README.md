# stix

[![GitHub release](https://img.shields.io/github/release/go-fonts/stix.svg)](https://github.com/go-fonts/stix/releases)
[![GoDoc](https://godoc.org/github.com/go-fonts/stix?status.svg)](https://godoc.org/github.com/go-fonts/stix)
[![License](https://img.shields.io/badge/License-BSD--3-blue.svg)](https://github.com/go-fonts/stix/raw/master/LICENSE)

`stix` provides the [STIX](https://www.stixfonts.org/) fonts as importable Go packages.

The fonts are released under the [SIL Open Font](https://github.com/go-fonts/stix/raw/master/SIL-LICENSE) license.
The Go packages under the [BSD-3](https://github.com/go-fonts/stix/raw/master/LICENSE) license.

## Example

```go
import (
	"fmt"
	"log"

	"github.com/go-fonts/stix/stix2math"
	"golang.org/x/image/font/sfnt"
)

func Example() {
	ttf, err := sfnt.Parse(stix2math.TTF)
	if err != nil {
		log.Fatalf("could not parse STIX2 Math font: %+v", err)
	}

	fmt.Printf("num glyphs: %d\n", ttf.NumGlyphs())

	// Output:
	// num glyphs: 5543
}
```
