---
title: Re-definition of the Update Tag
abbrev: Upadte Tag Definition
docname: draft-kuehlewind-update-tag-latest
date:
category: bcp

ipr: trust200902
keyword: Internet-Draft

stand_alone: yes
pi: [sortrefs, symrefs]

author:
  -
    ins: M. Kuehlewind
    name: Mirja Kuehlewind
    org: Ericsson
    email: mirja.kuehlewind@ericsson.com
  -
    ins: S. Krishnan
    name: Suresh Krishnan
    org: Kaloom
    email: Suresh@kaloom.com

normative:


informative:



--- abstract

The metadata of an RFC can include a tag called "Updates" which can be used to link a new RFC to an existing RFC. On publication of such an RFC, the existing RFC will include an additonal metadata tag called "Updated by" which provides a link to the new RFC. However, this tag pair is not well-defined and therefore it is currently used for multiple different cases, which leads to confusion about the actual meaning of this tag and inconsitency in its use.

This document recommends the discontinuation of the use of the updates/updated by tag pair, and instead proposes three new tag pairs that have well-defined meanings and use cases. 

--- middle

# Introduction

In metadata of an RFC can include a tag called "Updates" which can be used to link a new RFC to an existing RFC. On publication of such an RFC, the existing RFC will include an additonal metadata tag called "Updated by" which provides a link to the new RFC. However, this tag pair is not well-defined and therefore it is currently used for multiple different cases, which leads to confusion about the actual meaning of this tag and inconsitency in its use.

This document recommends the discontinuation of the use of the updates/updated by tag pair, and instead proposes three new tag pairs that have well-defined meanings and use cases.

# New Definitions

Amends/Amended by: This tag pair is used with an amending RFC that
changes the amended RFC. This could include bug fixes, behavior
changes etc. This is intended to specify mandatory changes to the
protocol. The goal of this tag pair is to signal to anyone looking to
implement the amended RFC that they MUST also implement the amending
RFC.

Extends/Extended by: This tag pair is used with an extending RFC that
defines an optional addition to the extended RFC. This can be used by
documents that use existing extension points or clarifications that do
not change existing protocol behavior. This signals to implementers
and protocol designers that there are changes to the extended RFC that
they need to consider but not necessarily implement.

See Also/See Also: This is intended as a catch-all tag where two
documents are related loosely but do not fit either of the above
categories. The main intention of this tag is to provide a forward
reference from the existing RFC to the RFCs that may be of interest to
read.

# Acknowledgments

