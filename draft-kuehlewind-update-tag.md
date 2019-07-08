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

In metadata of an RFC may contain a tag called "updates" which can be used to link a new RFC to an existing RFC. On publication on such a new RFC, the existing RFC will come an additonal metadata tag called "updated by" which provides a directly linking to the new RFC. However, the of tag pair is not well-defined and therefore it is currently used for multiple different cases which leads to confusion about the actual meaning of this tag and inconsitency in its use.

This document recommends to not use the updates/updated by tag pair anymore, and instead proposed three new tag pairs that have well-defined meanings and use cases, namely "amends"/"amended by", "extends"/"extended by" and "see also".

--- middle

# Introduction

In metadata of an RFC may contain a tag called "updates" which can be used to link a new RFC to an existing RFC. On publication on such a new RFC, the existing RFC will come an additonal metadata tag called "updated by" which provides a directly linking to the new RFC. However, the of tag pair is not well-defined and therefore it is currently used for multiple different cases which leads to confusion about the actual meaning of this tag and inconsitency in its use.

This document recommends to not use the updates/updated by tag pair anymore, and instead proposed three new tag pairs that have well-defined meanings and use cases, namely "amends"/"amended by", "extends"/"extended by" and "see also".

# New Definitions




# Acknowledgments

