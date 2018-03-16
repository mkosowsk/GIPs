    GIP: 1
      Title: GIP Purpose and Guidelines
      Status: Active
      Type: Meta
      Author: Martin Becze <mb@Ethereum.org>, Hudson Jameson <hudson@Ethereum.org> (EIPs).  Kevin Owocki (kevin@gitcoin.co) (GIPS)
      Created: 2015-10-27, 2017-02-01 (EIPs) 2019-03-12 (GIPs)

What is an GIP?
--------------

GIP stands for Gitcoin Improvement Proposal. An GIP is a design document providing information to the Gitcoin community, or describing a new feature for Gitcoin or its processes or environment. The GIP should provide a concise technical specification of the feature and a rationale for the feature. The GIP author is responsible for building consensus within the community and documenting dissenting opinions.

GIP Rational
------------

We intend GIPs to be the primary mechanisms for proposing new features, for collecting community input on an issue, and for documenting the design decisions that have gone into Gitcoin. Because the GIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Gitcoin implementers, GIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the GIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

GIP Types
---------

There are three types of GIP:

-   A **Standard Track GIP** describes any change that affects most or all Gitcoin implementations, such as a change to the the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Gitcoin. Furthermore Standard GIPs can be broken down into the following categories.
    -   **Core** - improvements requiring a consensus fork, as well as changes that are not necessarily consensus critical but may be relevant to “core dev” discussions.
    -   **Application** - includes improvements around and, as well as proposed improvements to application..
    -   **Interface** - includes improvements around client [API/web] specifications and standards. The label “interface” aligns with the [interfaces repo] and discussion should primarily occur in that repository before an GIP is submitted to the GIPs repository.
    -   **GRC** - application-level standards and conventions, including contract standards such as token standards, etc..

-   An **Informational GIP** describes a Gitcoin design issue, or provides general guidelines or information to the Gitcoin community, but does not propose a new feature. Informational GIPs do not necessarily represent Gitcoin community consensus or a recommendation, so users and implementers are free to ignore Informational GIPs or follow their advice.
-   A **Meta GIP** describes a process surrounding Gitcoin or proposes a change to (or an event in) a process. Process GIPs are like Standards Track GIPs but apply to areas other than the Gitcoin protocol itself. They may propose an implementation, but not to Gitcoin's codebase; they often require community consensus; unlike Informational GIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Gitcoin development. Any meta-GIP is also considered a Process GIP.

GIP Work Flow
-------------

The GIP repository Collaborators change the GIPs status. Please send all GIP-related email to the GIP Collaborators, which is listed under GIP Editors below. Also see GIP Editor Responsibilities & Workflow.

The GIP process begins with a new idea for Gitcoin. It is highly recommended that a single GIP contain a single key proposal or new idea. The more focused the GIP, the more successful it tends to be. A change to one client doesn't require an GIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does. The GIP editor reserves the right to reject GIP proposals if they appear too unfocused or too broad. If in doubt, split your GIP into several well-focused ones.

Each GIP must have a champion - someone who writes the GIP using the style and format described below, shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea.

Vetting an idea publicly before going as far as writing an GIP is meant to save the potential author time. Asking the Gitcoin community  first if an idea is original helps prevent too much time being spent on something that is guaranteed to be rejected based on prior discussions (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Gitcoin is used. Examples of appropriate public forums to gauge interest around your GIP include [the Gitcoin Slack], [the Issues section of this repository], and [one of the Gitcoin Gitter chat rooms]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your GIP. 

Once the champion has asked the Gitcoin community whether an idea has any chance of acceptance a draft GIP should be presented as a [pull request]. This gives the author a chance to continuously edit the draft GIP for proper formatting and quality. This also allows for further public comment and the author of the GIP to address concerns about the proposal.

If the GIP collaborators approve, the GIP editor will assign the GIP a number (generally the issue or PR number related to the GIP), label it as Standards Track, Informational, or Meta, give it status “Draft”, and add it to the git repository. The GIP editor will not unreasonably deny an GIP. Reasons for denying GIP status include duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Gitcoin philosophy.

Standards Track GIPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification]. The GIP should be reviewed and accepted before an implementation is begun, unless an implementation will aid people in studying the GIP. Standards Track GIPs must be implemented in at least three viable Gitcoin clients before it can be considered Final.

For an GIP to be accepted it must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

Once an GIP has been accepted, the implementations must be completed. When the implementation is complete and accepted by the community, the status will be changed to “Final”.

An GIP can also be assigned status “Deferred”. The GIP author or editor can assign the GIP this status when no progress is being made on the GIP. Once an GIP is deferred, the GIP editor can re-assign it to draft status.

An GIP can also be “Rejected”. Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

GIPs can also be superseded by a different GIP, rendering the original obsolete.

The possible paths of the status of GIPs are as follows:

<img src=./GIP-1/process.png>

Some Informational and Process GIPs may also have a status of “Active” if they are never meant to be completed. E.g. GIP 1 (this GIP).

What belongs in a successful GIP?
---------------------------------

Each GIP should have the following parts:

-   Preamble - RFC 822 style headers containing metadata about the GIP, including the GIP number, a short descriptive title (limited to a maximum of 44 characters), the names, and optionally the contact info for each author, etc.

<!-- -->

-   Simple Summary - “If you can’t explain it simply, you don’t understand it well enough.” Provide a simplified and layman-accessible explanation of the GIP.

<!-- -->

-   Abstract - a short (~200 word) description of the technical issue being addressed.

<!-- -->

-   Motivation (*optional) - The motivation is critical for GIPs that want to change the Gitcoin protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the GIP solves. GIP submissions without sufficient motivation may be rejected outright.

<!-- -->

-   Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Gitcoin platforms (cpp-Gitcoin, go-Gitcoin, parity, GitcoinJ, Gitcoinjs-lib, …).

<!-- -->

-   Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.

<!-- -->

-   Backwards Compatibility - All GIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The GIP must explain how the author proposes to deal with these incompatibilities. GIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

<!-- -->

-   Test Cases - Test cases for an implementation are mandatory for GIPs that are affecting consensus changes. Other GIPs can choose to include links to test cases if applicable.

<!-- -->

-   Implementations - The implementations must be completed before any GIP is given status “Final”, but it need not be completed before the GIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.

<!-- -->

-   Copyright Waiver - All GIPs must be in public domain. See the bottom of this GIP for an example copyright waiver.

GIP Formats and Templates
-------------------------

GIPs should be written in [markdown] format. Image files should be included in a subdirectory for that GIP.

GIP Header Preamble
-------------------

Each GIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` GIP: ` <GIP number> (this is determined by the GIP editor)

` Title: `<GIP title>

` Author: `<list of author's real names and optionally, email address>

` * Discussions-To: ` <email address> or slack channel

` Status: `<Draft | Active | Accepted | Deferred | Rejected | Withdrawn | Final | Superseded>

` Type: `<Standards Track (Core, Networking, Interface, GRC)  | Informational | Process>

` Created: `<date created on, in ISO 8601 (yyyy-mm-dd) format>

` * Replaces: `<GIP number>

` * Superseded-By: `<GIP number>

` * Resolution: `<url>

The Author header lists the names, and optionally the email addresses of all the authors/owners of the GIP. The format of the Author header value must be

Random J. User &lt;address@dom.ain&gt;

if the email address is included, and

Random J. User

if the email address is not given.

Note: The Resolution header is required for Standards Track GIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the GIP is made.

While an GIP is in private discussions (usually during the initial Draft phase), a Discussions-To header will indicate the mailing list or URL where the GIP is being discussed. No Discussions-To header is necessary if the GIP is being discussed privately with the author.

The Type header specifies the type of GIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or GRC).

The Created header records the date that the GIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

GIPs may have a Requires header, indicating the GIP numbers that this GIP depends on.

GIPs may also have a Superseded-By header indicating that an GIP has been rendered obsolete by a later document; the value is the number of the GIP that replaces the current document. The newer GIP must have a Replaces header containing the number of the GIP that it rendered obsolete.

Auxiliary Files
---------------

GIPs may include auxiliary files such as diagrams. Such files must be named GIP-XXXX-Y.ext, where “XXXX” is the GIP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).

Transferring GIP Ownership
--------------------------

It occasionally becomes necessary to transfer ownership of GIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred GIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the GIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the GIP. We try to build consensus around an GIP, but if that's not possible, you can always submit a competing GIP.

If you are interested in assuming ownership of an GIP, send a message asking to take over, addressed to both the original author and the GIP editor. If the original author doesn't respond to email in a timely manner, the GIP editor will make a unilateral decision (it's not like such decisions can't be reversed :).

GIP Editors
-----------

The current GIP editors are

 * Kevin Owocki (@owocki)`

 * Mark Beacom (@mbeacom)`

 * Mark Beylin (@mbeylin)`


GIP Editor Responsibilities and Workflow
--------------------------------------

For each new GIP that comes in, an editor does the following:

-   Read the GIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
-   The title should accurately describe the content.
-   Edit the GIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the GIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the GIP is ready for the repository, the GIP editor will:

-   Assign an GIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this GIP)

<!-- -->

-   Accept the corresponding pull request

<!-- -->

-   List the GIP in [README.md]

<!-- -->

-   Send a message back to the GIP author with next step.

Many GIPs are written and maintained by developers with write access to the Gitcoin codebase. The GIP editors monitor GIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on GIPs. We merely do the administrative & editorial part.

History
-------
N/A

Copyright
---------

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
