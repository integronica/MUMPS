# How MUMPS Got Its first Standard a Year Before ANSI

by Rochus Keller

July 7, 2026

Ask almost anyone when the MUMPS programming language was first standardized and you will hear the same answer: 1977, as ANSI X11.1-1977. It is the date in the Wikipedia infobox, in countless retrospectives, and in the bibliographies of papers that ought to know better. It is also wrong, or at least incomplete. The first formal MUMPS standard was an U.S. government publication issued in **January 1976**: the *NBS Handbook 118, MUMPS Language Standard*. 

I recently completed and published [an implementation of the MUMPS 1976 standard](https://github.com/rochus-keller/mumps/), and received many surprised reactions from people who had never heard of it before. So it makes sense to take a closer look at this standard and its history here.

## The problem: one language, seven dialects

MUMPS (Massachusetts General Hospital Utility Multi-Programming System) was born in 1966 in the Laboratory of Computer Science at Massachusetts General Hospital, where a team needed a time-sharing system on a minicomputer that no commercial vendor could then provide [^1]. The design was a striking success: up to twenty simultaneous users could share a database on a PDP-9 with just 32K words of memory [^2].

Success bred imitation, and imitation bred fragmentation. As different groups ported and enhanced MUMPS independently, the language splintered. By 1972, at least seven distinct dialects could be identified across the growing user community [^2]. This was more than an academic annoyance. The National Center for Health Services Research (NCHSR), part of the Department of Health, Education and Welfare (HEW), had hoped that MUMPS application packages written at one hospital could be freely shared with every other institution running MUMPS — avoiding wasteful duplication across a large base of federally funded medical systems. The proliferation of incompatible dialects made that portability increasingly impossible [^2].

## The response: NBS, a field study, and the birth of the MDC

To halt the divergence, the National Bureau of Standards (NBS), the Department of Commerce agency that would be renamed to "NIST" in 1988, was given a contract in 1972 to study the MUMPS dialects and make recommendations [^2]. The study's central recommendation was structural: create a body to steward the language. "As a result of this study, NBS recommended the formation of the MUMPS Development Committee (MDC)" [^2].

In the fall of 1972, the chief implementors and users of the competing dialects gathered at a conference in Boston, forming both the **MUMPS Users' Group (MUG)** and its sibling, the **MUMPS Development Committee (MDC)** [^3]. The MDC was funded with support from NCHSR and from NBS [^4].

Crucially, the MDC was **not** an internal government committee. Its constitution was explicitly **modeled after the ANSI X3 language standards committees**, and it drew members from both the vendors marketing MUMPS and the institutions using it [^2]. It was a genuine public, cross-industry body. Its constitution described it this way:

> "The MDC is an informal and voluntary organization of interested individuals, supported by their institutions, who contribute their efforts and resources to the end of developing a computer programming language, which meets the requirements of a wide range of applications. The results of MDC activities will be in the public domain with the intent of promoting MUMPS language commonality and compatibility among computers." [^2]

And its stated technical objective was explicitly to address the portability crisis:

> "An objective of the MDC is to make possible compatible, uniform MUMPS source programs and execution results with continued reduction in the number of changes necessary for conversion or interchange of source programs and data." [^2]

The initial meeting of the MDC was held in March 1973, with 35 institutions in its membership [^2].

## The work: from task group to a complete specification

Standardization was slow, deliberate work. The foundation for a MUMPS standard was laid out by a small language task group during 1973. By mid-1974, a consensus had emerged on the core features of the standard language, with the task group handling the fine details and documenting their results for approval by the full MDC membership [^2].

The MDC worked through a series of numbered releases. An early *Partial MUMPS Language Standard* (MDC/25) appeared on October 14, 1974, followed by an *Interim MUMPS Language Specification* (MDC 1/8) on February 10, 1975. The definitive documents came together in 1975 as three formally approved "Type A releases":

- **Part I — MUMPS Language Specification (MDC/28)**, the narrative description using a BNF metalanguage, adopted and approved as a Type A release on March 12, 1975.
- **Part II — MUMPS Transition Diagrams (MDC/33)**, a formal definition of the language via decision graphs, approved as a Type A release on September 17, 1975.
- **Part III — MUMPS Portability Requirements (MDC/34)**, setting maximum program limits and minimum implementation requirements, also approved as a Type A release on September 17, 1975.

Thus, in September 1975, a complete set of MUMPS specification was agreed upon and formally approved by the full MDC membership [^2]. The approved specifications were handed to NBS to be assembled and published as the first MUMPS standard.

## The publication: NBS Handbook 118, January 1976

Here the roles become important, and they are documented right in the front matter of the handbook.

The MDC's chairman, R. Peter Ericson of The Institute of Living in Hartford, Connecticut, wrote a Preface dated September 17, 1975, which was the same day the last two parts were approved. His wording is precise and telling:

> "The reader is hereby notified that **the language specifications contained in this Standard** have been approved by the MUMPS Development Committee..." [^1].

That single sentence draws the line between two things: the *language specifications* (the MDC's approved work) and *this Standard* (the document that contains them). They are not the same artifact, instead one is embedded within the other.

A few weeks later, on October 14, 1975, Ruth M. Davis, Director of NBS's Institute for Computer Sciences and Technology, signed the Foreword. It identifies each of the three parts by their MDC release numbers and approval dates, then describes the NBS role:

> "As a MUMPS user and charter member of the MUMPS Development Committee, the National Bureau of Standards is pleased to have the opportunity to make this information available through publication of this NBS Handbook." [^1]

The document then went to prepress and was **issued in January 1976** as **NBS Handbook 118, *MUMPS Language Standard***, edited by Joseph T. O'Neill of the Systems and Software Division, sponsored by NCHSR, and published under the U.S. Department of Commerce [^1].

The clean reading of the record is this: the MDC produced and approved the underlying language specifications in 1975; NBS then assembled, framed, and published them as a federal handbook titled *MUMPS Language Standard*. As the agency with an explicit federal mandate to serve as "the principal focus within the executive branch for the development of Federal standards for automatic data processing equipment, techniques, and computer languages," it gave the MDC's approved material the formal status of a U.S. government standard document. Why the hurry to publish rather than wait for ANSI? The government had a large installed base of federally funded MUMPS medical systems to protect, and no way of knowing how long a private standardization process might take. An immediately citable, authoritative federal reference protected that investment right away.

This was also a document with real reach. Several thousand copies were distributed in early 1976 to the mailing lists of the MDC and MUG, and because it was an NBS Handbook, it also went to over a thousand government repository libraries nationwide [^2].

## What ANSI did afterward

Only after the NBS Handbook was published did the ANSI process begin. The MUMPS Standard, together with its supporting documents, was submitted to the American National Standards Institute for approval [^2].

It is worth being clear about what ANSI is, because it is frequently confused with NBS. ANSI is a private, non-profit organization (founded 1918) that does not itself write standards; it accredits standards developers and coordinates the formal consensus process that confers the status of "American National Standard." NBS/NIST, by contrast, was and is a federal government agency. The 1988 renaming of NBS to NIST was an internal government reorganization, entirely unrelated to ANSI [^5].

The ANSI step was a ratification pass over largely the same material and the same community, not a fresh standardization from scratch. After public review throughout much of 1976 "by interested parties, including all member organizations of both the ANSI X3 Committee and the MDC", MUMPS was approved as an American National Standard, X11.1-1977, on September 15, 1977 [^2].

From there, the MDC continued to steward the language through a long series of revisions under ANSI's imprimatur: X11.1-1984, X11.1-1990, and X11.1-1995, plus a Federal Information Processing Standard (FIPS 125, later 125-1) and eventually an international standard, ISO/IEC 11756:1992 [^3]. Stewardship later passed to the M Technology Association, which ANSI accredited as a Standards Development Organization; when that body dissolved on January 1, 2002, its ANSI accreditation and standards lapsed, though the ISO standard was unaffected.

## Why the first standard was almost forgotten

If NBS Handbook 118 came first, was widely distributed, and explicitly called itself the *MUMPS Language Standard*, why does history reach past it to 1977? Several forces conspired:

1. Every subsequent MUMPS standard carried an ANSI designation (X11.1-1984, -1990, -1995). Later documents cite their predecessors, and that citation chain runs back to X11.1-1977 as its origin point — not to a one-off government handbook. Bibliographies follow the living series, not the document that seeded it.

2. When ISO adopted MUMPS as ISO/IEC 11756, it built on the ANSI text. National procurement and compliance references likewise pointed to the ANSI standard, cementing 1977 as the canonical anchor.

3. NBS Handbook 118 was distributed to repository libraries and mailing lists as a reference publication. To later readers unaware of its status, an "NBS Handbook" simply does not carry the same ring of authority as an "ANSI standard," even though the handbook's own Foreword and Preface repeatedly call it a Standard.

4. Encyclopedic summaries state that a standard "was complete by 1974" and "approved as ANSI X11.1-1977," collapsing the 1975 MDC approval and the 1976 NBS publication out of the narrative entirely [^3]. Once that compressed version propagated, the 1976 handbook effectively vanished from the popular account.

The irony is that the primary documents tell the fuller story cleanly. The MDC, a public, cross-industry committee modeled on ANSI's own X3 structure, did the substantive standardization work between 1973 and 1975. NBS packaged and issued it as the first formal, citable MUMPS standard in January 1976. ANSI's 1977 ratification, valuable as it was for procurement, international adoption, and the long revision series that followed, came second. The scanned handbook now sits quietly on bitsavers and in the NIST legacy archive, waiting for anyone who cares to check the dates on the title page [^1].


## References

- [^1] NBS Handbook 118, https://nvlpubs.nist.gov/nistpubs/Legacy/hb/nbshandbook118.pdf and https://archive.org/details/bitsavers_mumpsNBSHaageStandardJan1976_6795659
- [^2] Emerson & O'Neill, *The Evolution of a Language Standard*, ACM, https://dl.acm.org/doi/pdf/10.1145/800176.809935
- [^3] MUMPS, Wikipedia, https://en.wikipedia.org/wiki/MUMPS
- [^4] Becker Medical Library, Washington University, https://becker.wustl.edu/news/mumps-and-medical-computing/
- [^5] NIST history, https://www.nist.gov/nist-history

