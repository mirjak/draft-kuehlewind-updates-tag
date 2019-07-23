---
title: Definition of new tags for relations between RFCs
abbrev: New Tag Definitions
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

The metadata of an RFC can include a tag called "Updates" which can be used to
link a new RFC to an existing RFC. On publication of such an RFC, the existing
RFC will include an additional metadata tag called "Updated by" which provides a
link to the new RFC. However, this tag pair is not well-defined and therefore it
is currently used for multiple different purposes, which leads to confusion about
the actual meaning of this tag and inconsistency in its use.

This document recommends the discontinuation of the use of the updates/updated
by tag pair, and instead proposes three new tag pairs that have well-defined
meanings and use cases.

--- middle

# Introduction

The metadata of an RFC can include a tag called "Updates" which can be used to
link a new RFC to an existing RFC. On publication of such an RFC, the existing
RFC will include an additional metadata tag called "Updated by" which provides a
link to the new RFC. However, this tag pair is not well-defined and therefore it
is currently used for multiple different purposes, which leads to confusion about
the actual meaning of this tag and inconsistency in its use.

The "Updates/Updates by" tag pair is currently used by different working groups and
different areas, which tend to apply different meanings to it. They also differ greatly 
about the obligations on the implementors of the Updated RFC. While updating an RFC never
makes the updated RFC invalid, updates can contain bug fixes or critical changes.
Some groups apply the update tag only to these kind of changes with the
expectation that new implementors are also obliged to implement this new
RFC. Some other groups use the update tag to define optional extensions or use of extension
points in the current protocol. This disconnect leads to a situation where it is desirable 
to add at "mandatory-to-implement" indication to an existing RFC.

Groups or individuals that apply such restrictive conditions to the updates tag,
consequently usually don't use the update tag for any extensions or addition to
a protocol. However, as there is no other way in the current metadata scheme to
link a new RFC to an existing RFC, not using the updates tag makes it harder to
find these new RFCs. While new implementors might well benefit from some
extensions or additions, they might not be aware of them and ether not use them
or, in the worst case, implement a proprietary mechanism instead.

Currently the Updates/Updated by tag pair mainly provides a way to link two
documents. The cases mentioned above clearly benefit from such a linkage
which the expectation that readers of one RFC as least look or also read the other
RFC. Additionally, there are more cases where such a linkage could be useful to improve
awareness of some newer related technology without providing any indication on the 
importance of the linked document. As the conditions for the use of the updates tag 
are not clear, often it is not used in such cases.

This document recommends the discontinuation of the use of the Updates/Updated
by tag pair, and instead proposes three new tag pairs that have well-defined
meanings and use cases.

# New Definitions

Based on the problems identified above this document defines three new tag pairs
with the following meanings:

Amends/Amended by: This tag pair is used with an amending RFC that changes the
amended RFC. This could include bug fixes, behavior changes etc. This is
intended to specify mandatory changes to the protocol. The goal of this tag pair
is to signal to anyone looking to implement the amended RFC that they MUST also
implement the amending RFC.

Extends/Extended by: This tag pair is used with an extending RFC that defines an
optional addition to the extended RFC. This can be used by documents that use
existing extension points or clarifications that do not change existing protocol
behavior. This signals to implementers and protocol designers that there are
changes to the extended RFC that they need to consider but not necessarily
implement.

See Also/See Also: This is intended as a catch-all tag where two documents are
related loosely but do not fit either of the above categories. The main
intention of this tag is to provide a forward reference from the existing RFC to
the RFCs that may be of interest to read.

These three tags MUST only be used for the defined meanings, mostly with respect
to the implication on implementation requirements. This document does
not mandate the use of these tags if one of the described use cases apply. Tags
are optional metadata that are meant to help understanding an RFC and navigate
the RFC series, however, they do not have normative implications on the
protocol specification within the RFC.

# Additional Recommendation

## Discontinuation of the Use of Updates/Updated by

While this document does not declare the updates tag obsolete, it gives a
strong recommendation to no longer use it for new IETF stream documents. 
However, the Updates/Updated by tag pair will remain in existing documents 
and there is no plans to change these metadata in order to apply the new tags
instead. Any such change would need working group consensus as it might not be
straight forward in all cases. Further, simply replacing the tag would not be
sufficient, as also RFCs that currently do not have an updates tag would probably
qualify to have one of the new tags defined in this document.

## Amendments

This document does not impose any requirements on the form of the amendment
made. Some RFCs use and OLD/NEW style to highlight actual text changes others
simply describe the changes in text. Both can make sense in certain situation.
However, this document does recommend to use the OLD/NEW rather for smaller and
a limited number of changes, while if larger or many changes are needed, a new
document revision that obsoletes the old RFC should be considered.

## Indication of Linkage in the Abstract and Introduction

The RFC style guide (add ref!) recommends to indicate updates in the abstract
and introduction. Note that both is needed as the abstract is meant to function
in a stand-alone fashion. This document will keep this practice for the new
Amends/Amended by and Extends/Extended by tag pairs as well. It is further
recommended to provide additional information about the extension in the
abstract or introduction for the Extends/Extended by tag pair in order to
provide the reader some assistance whether he or she also needs to read the rest
of extending RFC.

For the See Also/See Also tag pair, additional information of the linked RFC may
be added in the introduction but there is no expectation to name these RFC in
the abstract.

# Acknowledgments

