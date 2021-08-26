---
title: "Bootstrapping WebSockets with HTTP/3"
docname: draft-hamilton-httpbis-h3-websockets
category: info

ipr: trust200902
area: TODO
workgroup: HTTP
keyword: Internet-Draft

stand_alone: yes
smart_quotes: no
pi: [toc, sortrefs, symrefs]

author:
 -
    name: Ryan Hamilton
    organization: Google
    email: rch@google.com

normative:

informative:


--- abstract

The mechanism for running the WebSocket Protocol over a single stream
of an HTTP/3 connection is equally applicable to HTTP/3, but need to be
separately registered.  This document describes the
SETTINGS_ENABLE_CONNECT_PROTOCOL SETTINGS Parameter for HTTP/3.

--- middle

# Introduction

{{!RFC8441}} defines an extension to HTTP/2 which is also useful in HTTP/3.
Appendix A.2.3 of [HTTP3] describes the required updates for HTTP/2
settings to be used with HTTP/3.


# Conventions and Definitions

{::boilerplate bcp14-tagged}

{{!RFC8441}} defines a mechanism for running the WebSocket Protocol
{{!RFC6455}} over a single stream of an HTTP/2 connection. This includes
the use of a new HTTP/2 SETTING send by a server to inform a client
that it may send the Extended CONNECT.

The semantics of the headers and SETTING are identical to those
in HTTP/2 as defined {{!RFC8441}}. The SETTINGS_ENABLE_CONNECT_PROTOCOL
value is 0x08 (decimal 8), as in HTTP/2.


# Security Considerations

This document introduces no new security considerations beyond those
discussed in {{!RFC8841}}.



# IANA Considerations

This document registers a new setting in the "HTTP/3 Settings"
registry ([HTTP3]).


| -------------------------------- | ------- | -------------------- | ------- |
| Setting Name                     |  Value  | Specification        | Default |
| -------------------------------- | :-----: | -------------------- | ------- |
| SETTINGS_ENABLE_CONNECT_PROTOCOL |  0x08   | This document        | 0       |
| -------------------------------- | ------- | -------------------- | ------- |



--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
