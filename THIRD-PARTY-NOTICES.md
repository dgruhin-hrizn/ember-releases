# Third-party notices

Ember is proprietary software (see [LICENSE](LICENSE)). It is built on, and ships with, the open-source software and
assets below. Each stays under its own licence, and Ember's licence does not limit your rights under those licences
for those components on their own.

The application also carries its own notice files, which are the complete record for the version you have installed:
`LICENSE.txt` and `ThirdPartyNotices.txt` (the editor Ember is built on) and `LICENSES.chromium.html` (Electron and
Chromium), in the application's resources folder.

Product names and logos shown in Ember belong to their owners and are used only to identify the service or project
they stand for.

## The editor Ember is built on

### VSCodium and Code - OSS

Ember.app is a build of [VSCodium](https://github.com/VSCodium/vscodium), which is built from Microsoft's
[Code - OSS](https://github.com/microsoft/vscode) (Visual Studio Code's open-source code). Licensed under the MIT
License:

    MIT License

    Copyright (c) 2018-present The VSCodium contributors
    Copyright (c) 2018-present Peter Squicciarini
    Copyright (c) 2015-present Microsoft Corporation

(The MIT License text is under "Licence texts" below.)

The many packages inside Code - OSS are listed, with their licences, in `ThirdPartyNotices.txt` inside the
application.

### Electron and Chromium

The editor runs on [Electron](https://github.com/electron/electron) (MIT License, Copyright (c) Electron contributors,
Copyright (c) 2013-2020 GitHub Inc.), which includes Chromium and Node.js. Their licences, and those of the software
they include, are in `LICENSES.chromium.html` inside the application.

## Software in Ember's own parts

| Component | Used for | Copyright | Licence |
|---|---|---|---|
| [React](https://github.com/facebook/react) (`react`, `react-dom`) | Ember's views and canvases | Copyright (c) Meta Platforms, Inc. and affiliates | MIT |
| [Apache ECharts](https://github.com/apache/echarts) (`echarts`) | The usage dashboard's charts | Copyright 2017-2026 The Apache Software Foundation | Apache-2.0 |
| [ZRender](https://github.com/ecomfe/zrender) (`zrender`) | ECharts' rendering engine | Copyright (c) 2017, Baidu Inc. All rights reserved. | BSD-3-Clause |
| [beautiful-mermaid](https://www.npmjs.com/package/beautiful-mermaid) | Mermaid diagrams in chats and file previews | Copyright (c) 2026 Craft Docs | MIT |
| [Sucrase](https://github.com/alangpierce/sucrase) | Compiles canvases | Copyright (c) 2012-2018 various contributors, Copyright (c) 2018 Alan Pierce | MIT |
| [Lucide](https://github.com/lucide-icons/lucide) (`lucide-react`) | Line icons on tool rows in the chat | Copyright (c) 2026 Lucide Icons and Contributors; some icons derive from Feather, Copyright (c) 2013-present Cole Bemis | ISC, MIT |
| [jsdiff](https://github.com/kpdecker/jsdiff) (`diff`) | Text differences | Copyright (c) 2009-2015, Kevin Decker | BSD-3-Clause |
| [jsonc-parser](https://github.com/microsoft/node-jsonc-parser) | Reads settings files with comments | Copyright (c) Microsoft | MIT |
| [picomatch](https://github.com/micromatch/picomatch) | File patterns | Copyright (c) 2017-present, Jon Schlinkert | MIT |
| [node-qrcode](https://github.com/soldair/node-qrcode) (`qrcode`) | The QR code for pairing a phone | Ryan Day | MIT |
| [ws](https://github.com/websockets/ws) | WebSocket connections | Copyright (c) 2011 Einar Otto Stangvik, Copyright (c) 2013 Arnout Kazemier and contributors, Copyright (c) 2016 Luigi Pinca and contributors | MIT |
| [yaml](https://github.com/eemeli/yaml) | Reads YAML | Copyright Eemeli Aro | ISC |
| [Zod](https://github.com/colinhacks/zod) | Checks data shapes | Copyright (c) 2025 Colin McDonnell | MIT |
| [react-markdown](https://github.com/remarkjs/react-markdown), [remark](https://github.com/remarkjs/remark), [unified](https://github.com/unifiedjs/unified) | Renders Markdown in chats and Help | Copyright (c) Espen Hovlandsdal; Copyright (c) Titus Wormer | MIT |

Apache ECharts' NOTICE:

> Apache ECharts
> Copyright 2017-2026 The Apache Software Foundation
>
> This product includes software developed at The Apache Software Foundation (https://www.apache.org/).

## Icons, logos and schemas

| Component | Used for | Copyright | Licence |
|---|---|---|---|
| [Lobe Icons](https://github.com/lobehub/lobe-icons) (`@lobehub/icons-static-svg`) | Model provider icons | Copyright (c) LobeHub | MIT |
| [Simple Icons](https://github.com/simple-icons/simple-icons) | Tailscale, ngrok and Cloudflare marks in Settings | | CC0 1.0 Universal |
| [Logos](https://github.com/gilbarbara/logos) (`@iconify-json/logos`) | Brand logos beside MCP tool calls | | CC0 1.0 Universal |
| [SchemaStore](https://github.com/SchemaStore/schemastore) `claude-code-settings.json` | Completes and checks Claude Code settings files | | Apache-2.0 |

## Fonts

| Font | Used for | Copyright | Licence |
|---|---|---|---|
| [Inter](https://github.com/rsms/inter) | The font of Ember's views | Copyright 2016 The Inter Project Authors | SIL Open Font License 1.1 |
| [Source Serif 4](https://github.com/adobe-fonts/source-serif) | Headings in Ember's views | Copyright 2014–2023 Adobe (http://www.adobe.com/), with Reserved Font Name 'Source' | SIL Open Font License 1.1 |
| [JetBrains Mono](https://github.com/JetBrains/JetBrainsMono) | Ember's code font, in its views, the editor and the terminal | Copyright 2020 The JetBrains Mono Project Authors | SIL Open Font License 1.1 |

## Not bundled: downloaded or installed separately

- **Claude Code CLI and the Claude Agent SDK.** Ember runs chats through Anthropic's Claude Code. You install the CLI
  yourself; Ember includes Anthropic's Claude Agent SDK (`@anthropic-ai/claude-agent-sdk`) to talk to it. Both are
  © Anthropic PBC, all rights reserved, and their use is subject to Anthropic's legal agreements:
  https://code.claude.com/docs/en/legal-and-compliance. They are not open source.
- **CLIProxyAPI** ([router-for-me/CLIProxyAPI](https://github.com/router-for-me/CLIProxyAPI)), the model bridge. Not
  bundled with Ember: when you turn the bridge on, Ember downloads a published release from GitHub into its own
  storage, checks it against the release's checksums, and keeps the release's own `LICENSE` file next to it.
  Copyright (c) 2025-2005.9 Luis Pater. Copyright (c) 2025.9-present Router-For.ME. MIT License.

## Licence texts

### MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated
documentation files (the "Software"), to deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the
Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE
WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

### BSD 3-Clause License

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the
following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following
   disclaimer.
2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following
   disclaimer in the documentation and/or other materials provided with the distribution.
3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote
   products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES,
INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

### ISC License (Lucide), with the Feather notice

    ISC License
    
    Copyright (c) 2026 Lucide Icons and Contributors
    
    Permission to use, copy, modify, and/or distribute this software for any
    purpose with or without fee is hereby granted, provided that the above
    copyright notice and this permission notice appear in all copies.
    
    THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
    WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
    MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
    ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
    WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
    ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
    OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
    
    ---
    
    The following Lucide icons are derived from the Feather project:
    
    airplay, alert-circle, alert-octagon, alert-triangle, aperture, arrow-down-circle, arrow-down-left, arrow-down-right, arrow-down, arrow-left-circle, arrow-left, arrow-right-circle, arrow-right, arrow-up-circle, arrow-up-left, arrow-up-right, arrow-up, at-sign, calendar, cast, check, chevron-down, chevron-left, chevron-right, chevron-up, chevrons-down, chevrons-left, chevrons-right, chevrons-up, circle, clipboard, clock, code, columns, command, compass, corner-down-left, corner-down-right, corner-left-down, corner-left-up, corner-right-down, corner-right-up, corner-up-left, corner-up-right, crosshair, database, divide-circle, divide-square, dollar-sign, download, external-link, feather, frown, hash, headphones, help-circle, info, italic, key, layout, life-buoy, link-2, link, loader, lock, log-in, log-out, maximize, meh, minimize, minimize-2, minus-circle, minus-square, minus, monitor, moon, more-horizontal, more-vertical, move, music, navigation-2, navigation, octagon, pause-circle, percent, plus-circle, plus-square, plus, power, radio, rss, search, server, share, shopping-bag, sidebar, smartphone, smile, square, table-2, tablet, target, terminal, trash-2, trash, triangle, tv, type, upload, x-circle, x-octagon, x-square, x, zoom-in, zoom-out
    
    The MIT License (MIT) (for the icons listed above)
    
    Copyright (c) 2013-present Cole Bemis
    
    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:
    
    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.
    
    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.

### Apache License 2.0

https://www.apache.org/licenses/LICENSE-2.0

### CC0 1.0 Universal

https://creativecommons.org/publicdomain/zero/1.0/legalcode

### SIL Open Font License 1.1

    -----------------------------------------------------------
    SIL OPEN FONT LICENSE Version 1.1 - 26 February 2007
    -----------------------------------------------------------

    PREAMBLE
    The goals of the Open Font License (OFL) are to stimulate worldwide
    development of collaborative font projects, to support the font creation
    efforts of academic and linguistic communities, and to provide a free and
    open framework in which fonts may be shared and improved in partnership
    with others.

    The OFL allows the licensed fonts to be used, studied, modified and
    redistributed freely as long as they are not sold by themselves. The
    fonts, including any derivative works, can be bundled, embedded,
    redistributed and/or sold with any software provided that any reserved
    names are not used by derivative works. The fonts and derivatives,
    however, cannot be released under any other type of license. The
    requirement for fonts to remain under this license does not apply
    to any document created using the fonts or their derivatives.

    DEFINITIONS
    "Font Software" refers to the set of files released by the Copyright
    Holder(s) under this license and clearly marked as such. This may
    include source files, build scripts and documentation.

    "Reserved Font Name" refers to any names specified as such after the
    copyright statement(s).

    "Original Version" refers to the collection of Font Software components as
    distributed by the Copyright Holder(s).

    "Modified Version" refers to any derivative made by adding to, deleting,
    or substituting -- in part or in whole -- any of the components of the
    Original Version, by changing formats or by porting the Font Software to a
    new environment.

    "Author" refers to any designer, engineer, programmer, technical
    writer or other person who contributed to the Font Software.

    PERMISSION & CONDITIONS
    Permission is hereby granted, free of charge, to any person obtaining
    a copy of the Font Software, to use, study, copy, merge, embed, modify,
    redistribute, and sell modified and unmodified copies of the Font
    Software, subject to the following conditions:

    1) Neither the Font Software nor any of its individual components,
    in Original or Modified Versions, may be sold by itself.

    2) Original or Modified Versions of the Font Software may be bundled,
    redistributed and/or sold with any software, provided that each copy
    contains the above copyright notice and this license. These can be
    included either as stand-alone text files, human-readable headers or
    in the appropriate machine-readable metadata fields within text or
    binary files as long as those fields can be easily viewed by the user.

    3) No Modified Version of the Font Software may use the Reserved Font
    Name(s) unless explicit written permission is granted by the corresponding
    Copyright Holder. This restriction only applies to the primary font name as
    presented to the users.

    4) The name(s) of the Copyright Holder(s) or the Author(s) of the Font
    Software shall not be used to promote, endorse or advertise any
    Modified Version, except to acknowledge the contribution(s) of the
    Copyright Holder(s) and the Author(s) or with their explicit written
    permission.

    5) The Font Software, modified or unmodified, in part or in whole,
    must be distributed entirely under this license, and must not be
    distributed under any other license. The requirement for fonts to
    remain under this license does not apply to any document created
    using the Font Software.

    TERMINATION
    This license becomes null and void if any of the above conditions are
    not met.

    DISCLAIMER
    THE FONT SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
    EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTIES OF
    MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
    OF COPYRIGHT, PATENT, TRADEMARK, OR OTHER RIGHT. IN NO EVENT SHALL THE
    COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
    INCLUDING ANY GENERAL, SPECIAL, INDIRECT, INCIDENTAL, OR CONSEQUENTIAL
    DAMAGES, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
    FROM, OUT OF THE USE OR INABILITY TO USE THE FONT SOFTWARE OR FROM
    OTHER DEALINGS IN THE FONT SOFTWARE.
