# Really Simple Discoverability 1.0.0

Link to original RFC: [Really Simple Discoverability 1.0.0](http://archipelago.phrasewise.com/rsd)

Thu, Oct 31, 2002; by Daniel Berlinger (@danielberlinger):
> Really Simple Discoverability is a way to help client software find the services needed to read, edit, or "work with" weblogging software. 
> Although I talk about weblogging software, there's no reason this format can't apply to other forms of web client/system software that I wasn't considering, or may not even exist as of this writing. 
> This format is simple but flexible. One of the deisgn goals was to ensure that it would be human writeable. 
> This was my "test" for ensuring that the format was easy for everyone to implement.

**The goal is simple. To reduce the information required to UserName, Password, and homepage URL.**

## The Problem

Communicating with services requires knowledge about the service whereabouts and settings.
Specifically, discovering the "Path To Service" setting, but more generally where to point for services is a common issue.

## Proposed Solution

The solution proposed below will simplify the discovery of settings information by reducing the information a user must supply to three well known elements. 
Something simple, like an XML document that lists the critical info would be about right. It should also be simple enough to be written by hand. 
This document is called **Really Simple Discoverability**, or *RSD* document.

Assuming that the RSD file is provided or generated by the service software the other required bits of information not well known to the user can be easliy discovered and supplied.
The goal is to reduce the information required to set up service communication to three well known elements: **UserName**, **Password**, and **root URL**. 
Any other critical bits should either be defined in the related RSD file, or discoverable using the information provided.

A link similar to the RSS link burried into blogs would serve the purpose here.
By inserting a link into a homepage's HTML head section we uncouple the need to know where to find the RSD file. 
The link relationship is expressed in the following format:
```<link rel="RSD" type="application/rsd+xml" href="http://www.userdomain.com/rsd.xml" />```

Each service provider can control where it makes sense for them to *"place"* the RSD file, accessible via the embedded URL.
Client software only need to look at the homepage headers to discover where to look for more information.

A *"best practice"* location that represents the location where clients can try to find the file in cases where the link above has been removed, broken, or simply is not present, would be the following:
`http://www.userdomain.com/rsd.xml`.

## Elements

<table>
<tr>
<th>Element</th>
<th>Description</th>
</tr>
<tr>
<td>
`<rsd>`
</td>
<td>
RSD document root element
</td>
</tr>
<tr>
<td>
`<service>`
</td>
<td>
Container element. The RSD document can contain one or more service elements.
</td>
</tr>
</table>

## Copyright & Disclaimer

© Copyright 2002 Circumstance Technology. All Rights Reserved. This document and translations of it may be copied and furnished to others, and derivative works that comment on or otherwise explain it or assist in its implementation may be prepared, copied, published and distributed, in whole or in part, without restriction of any kind, provided that the above copyright notice and these paragraphs are included on all such copies and derivative works.

This document may not be modified in any way, such as by removing the copyright notice or references to Circumstance Technology or other organizations. Further, while these copyright restrictions apply to the written RSD specification, no claim of ownership is made by Circumstance Technology to the format it describes. Any party may, for commercial or non-commercial purposes, implement this format without royalty or license fee to Circumstance Technology. The limited permissions granted herein are perpetual and will not be revoked by Circumstance Technology or its successors or assigns.

This document and the information contained herein is provided on an "AS IS" basis and CIRCUMSTANCE TECHNOLOGY DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTY THAT THE USE OF THE INFORMATION HEREIN WILL NOT INFRINGE ANY RIGHTS OR ANY IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.
