# Minos - The Intuitive CSS Grid System

Minos is a flexbox-based CSS grid system that uses attribute selectors as the main medium for layout definition.

A layout is composed by three elements: container, grid, column. The container element defines a section with a maximum width in pixels according to the `--grid-container-width` property. Columns must be placed within grid elements.

## Installation

```
$ npm install Jaiheravi/Minos#master
```

## Use

```HTML
<div container>
  <div grid>
    <div column='x'>A simple column with x width</div>
    <div column='x +y'>A simple column with x width and y offset</div>
  </div>
</div>
```

## HTML Attributes

`container`
Sets the element as a container, the container element will have a max-width and will be centered on the page.

`grid`
Sets the element as a grid element. This is a required element, and should be direct parent of the column elements.

`column`
Sets the element as a column, should always be used inside a grid element. A column can also contain a grid element to nest grids.

## Attribute values

### Container

`solid`
The width of the container will be static across each breakpoint.

### Grid

`no-gutter`
Will create a grid where the columns don't have gutters.

`top`
Aligns all the columns inside vertically to the top of the grid.

`center`
Aligns all the columns inside vertically to the center of the grid.

`bottom`
Aligns all the columns inside vertically to the bottom of the grid.


### Column

`<width>`
The width of the column, by default from 1 to 12.

`+<offset>`
The offset of the column, by default from 1 to 11.

`top`
Aligns the column vertically to the top of the grid.

`center`
Aligns the column vertically to the center of the grid.

`bottom`
Aligns the column vertically to the bottom of the grid.


## Custom Properties

`--grid-container-width` <br>
**Default:** 1200px <br>
**Description**: Maximum width of the container element.

`--grid-gutter` <br>
**Default:** 2em <br>
**Description:** Space between columns.

## Breakpoints

`--small` <br>
**Value:** width >= 480px <br>
**Description**: Maximum width of the container element.

`--medium` <br>
**Value:** width >= 768px <br>
**Description:** Space between columns.

`--large` <br>
**Value:** width >= 960px <br>
**Description:** Space between columns.

## Examples

### Columns with a determined width

```HTML
<div grid>
  <section column="8">
    <p>8</p>
  </section>

  <section column="4">
    <p>4</p>
  </section>
</div>
```

### Columns without gutters

```HTML
<div grid="no-gutter">
  <section column="8">
    <p>8</p>
  </section>

  <section column="4">
    <p>4</p>
  </section>
</div>
```

### Columns with offsets

```HTML
<div grid>
  <section column="3">
    <p>3</p>
  </section>

  <section column="3 +6">
    <p>3 +6</p>
  </section>
</div>
```

### Columns with offsets and without gutters

```HTML
<div grid="no-gutter">
  <section column="5">
    <p>5</p>
  </section>

  <section column="5 +2">
    <p>5 +2</p>
  </section>
</div>
```

### Nested grids

```HTML
<div grid>
  <section column="4">
    <p>4</p>
  </section>

  <section column="8">
    <div grid>
      <section column="6">
        <p>6 inside 8</p>
      </section>

      <section column="6">
        <p>6 inside 8</p>
      </section>
    </div>
  </section>
</div>
```

### Nested grids without gutters

```HTML
<div grid="no-gutter">
  <section column="4">
    <p>4</p>
  </section>

  <section column="8">
    <div grid="no-gutter">
      <section column="6">
        <p>6 > 8</p>
      </section>

      <section column="6">
        <p>6 > 8</p>
      </section>
    </div>
  </section>
</div>
```

## License

Copyright (c) 2020 Jaime Hernández. All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
this list of conditions and the following disclaimer in the documentation and/or
other materials provided with the distribution.

3. All advertising materials mentioning features or use of this software must
display the following acknowledgement: This product includes software developed
by Jaime Hernández.

4. Neither the name of the copyright holder nor the names of its contributors
may be used to endorse or promote products derived from this software without
specific prior written permission.

THIS SOFTWARE IS PROVIDED BY COPYRIGHT HOLDER "AS IS" AND ANY EXPRESS OR IMPLIED
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT
SHALL COPYRIGHT HOLDER BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT
OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING
IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY
OF SUCH DAMAGE.
