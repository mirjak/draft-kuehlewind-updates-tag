---
title: Definition of new tags for relations between RFCs
abbrev: New Tag Definitions
docname: draft-kuehlewind-update-tag-latest
date:
category: bcp

ipr: trust200902
keyword: Internet-Draft

stand_alone: yes
pi: [toc, sortrefs, symrefs]

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

An RFC can include a tag called "Updates" which can be used to
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

An RFC can include a tag called "Updates" which can be used to
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
to add a "mandatory-to-implement" indication to an existing RFC.

Groups or individuals that apply such restrictive conditions to the Updates tag,
consequently usually don't use the update tag for any extensions or addition to
a protocol. However, as there is no other way in the current metadata scheme to
link a new RFC to an existing RFC, not using the Updates tag makes it harder to
find these new RFCs. While implementors might well benefit from some
extensions or additions, they might not be aware of them and either not use them
or, in the worst case, implement an alternate mechanism instead.

Currently the Updates/Updated by tag pair mainly provides a way to link two
documents. The cases mentioned above clearly benefit from such a linkage
which the expectation that readers of one RFC as least look or also read the other
RFC. Additionally, there are more cases where such a linkage could be useful to improve
awareness of some newer related technology without providing any indication on the 
importance of the linked document. As the conditions for the use of the Updates tag 
are not clear, often it is not used in such cases.

This document recommends the discontinuation of the use of the Updates/Updated
by tag pair, and instead proposes three new tag pairs that have well-defined
meanings and use cases.

# Requirements Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED",
"MAY", and "OPTIONAL" in this document are to be interpreted as
described in BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they
appear in all capitals, as shown here.
      
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
the RFCs that may be of interest to read. However, it is not recommenced to
use this tag extensively. 

These three tags MUST only be used for the defined meanings, mostly with respect
to the implication on implementation requirements. This document does
not mandate the use of these tags if one of the described use cases apply. Tags
are optional metadata that are useful to understand the context of RFCs and navigate
the RFC series. All three tags can only be used to reference other RFCs (and not as
reference to external sources).

As today with "updates", none of the new tags makes the extended/amended
RFC invalid. An implementation that conforms to the amended RFC still conforms
to that RFC, even when an amendment is published. However, an implementation
can, and hopefully should, of course be updated to also conform to the new RFC 
with the amendment. If only conformance to the new RFC is desired, obsoleting
the respective RFC with a new full (bis) specification may be more appropriate and
should be consider instead.

This document does not impose any restrictions on the status or maturity level of
the RFC that uses these new tags in relation the RFC that gets amended/extended.
Further, no restrictions are made on the use of these tags across RFC streams.
However, it is expected that some cases are less likely, e.g. an IETF-stream
RFC gets amended by an RFC from another stream. Examples exist where non
IETF-stream documents update IETF-stream documents. However, these updates usually
utilize an existing extension point and therefore the use of "Extends" would be expected
in future, e.g. RFC 3579 (RADIUS Support For EAP) which is a document in the
Independent Submission Stream updates RFC 2869 (RADIUS Extensions), an IETF stream
document. In fact, this new, more clear definition of tags could even lead to
an increase in cross stream usage of the "Extends" tag (if adopted by other
streams, which is still open for discussion and may be reflected in future versions
of this document).

# Additional Recommendations

## Discontinuation of the Use of Updates/Updated by

\[NOTE: This is open for discussion and we would like opinions on 
whether the use of Updates needs to be discontinued for all future 
documents or not. This requires further discussion with the 
RFC Editor and the other stream managers to see if we can have a 
unified policy for all streams\]

This document makes the updates tag obsolete for future use: it MUST NOT
be used in new IETF stream documents.  The new tags are to be used
instead, beginning with the publication of this document as an RFC.

However, the Updates/Updated by tag pair will remain in existing documents 
and there is no plans to change these metadata in order to apply the new tags
instead. Any such change would require changing/updating/amending the RFC
carrying the "Updates" tag and building consensus for such a change might also not
be straight forward in all cases. Further, simply replacing the tag would any way
not be sufficient, as also RFCs that currently do not have an updates tag would
probably qualify to have one of the new tags defined in this document.

## Amendments

This document does not impose any requirements on the form of the amendment
made. Some RFCs use and OLD/NEW style to highlight actual text changes others
simply describe the changes in text. Both can make sense in certain situation.
However, this document does recommend to use the OLD/NEW rather for smaller and
a limited number of changes, while if larger or many changes are needed, a new
document revision that obsoletes the old RFC should be considered.

## Indication of Linkage in the Abstract and Introduction

The RFC style guide {{!RFC7322}} recommends to indicate updates in the abstract
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

# Future work

There will be a need to update the RFC Style Guide {{RFC7322}} (and specifically
Section 4.1.4.) in order to discuss the new tags if and when this document is
published.

Further, the "updates" attribute is part of the "xml2rfc" Version 3 Vocabulary {{?RFC7991}}. 
Therefore an extension to {{RFC7991}} is need as well. This may be done by a future version of
this draft or in a separate draft, e.g. with other extension or amendments to {{RFC7991}}.

# Alternative Approaches

This document proposes three new meta data tag pairs to address the problem that the use of
the "Updates" tag is currently undefined which causes confusion due to various different practices
applied in different group and after all a waste of time in recurring discussion about using
or not using the tag.

Alternatively, in order to solely solve the problem of avoiding unnessecariy discussion time, it would
also be possible to document that the "Updates" tag is undefined and as such there are no 
strict rules about applying it or any implications of using it. This was proposed by the IESG
providing an IESG statement for community discussion and lead to community feedback indicating 
that this solution is not preferred.

However, rather than defining three new tags, one could also just clearly define the meaning of the existing
update tag. Stiill, this could also be confusing as it would not apply to RFCs that are already published.
So re-naming and defining one tags, instead of three, would be an alternative. This one tag
could either cover all three usages that are described in this draft or only one (probably the one
as definded by the proposed "Amends" tag, as this is usually seen as the most important one).

This draft proposed three tags as those tags are considered to cover most of the usages that we
see today for the "Updates" tag, assuming that these cases are benefiting from a forward reference
of an already published RFC to a new RFC. Especially separating changes to an existing RFC, as often done
by use of the OLD/NEW notation, from extension/additions to an RFC is one of the main confusion and 
discussion points and therefore this draft proposes different tags for it. However, if it shows that
not all proposed tags are actively used in future, or their usage is still not sufficiently clear,
it should be considered to deprecate the unused tags and therefore restrict forward references to
only some of the identified usages.


# Security Considerations

The changes in this document do not have direct impact on the security of any protocol
or mechanism specified in the RFC series. However, amendments or extensions can help
to improve security or discuss security-related issues. Therefore, the use of the
proposed tags and their clear definition can also support such RFCs in their intended
goals regarding security.

# Acknowledgments

The authors would like to thank Alexey Melnikov, Alvaro Retana, Barry Leiba,
Eric Vyncke, Heather Flanagan, Martin Vigoureux, Brian Carpenter and Sandy
Ginoza for their reviews and comments that improved this document. 
