<pre>
    BAIP: 001
      Title: BAIP Purpose and Guidelines
      Status: Active
      Type: Process
      Author: Aleksey Karpov admin@bitcoinasset.org
      Created: 2017-09-22
</pre>


What is an BAIP?
--------------
BAIP stands for Bitcoin Improvement Proposal.A BAIP is a design document providing information to the Bitcoin community, or describing a new feature for Bitcoin Asset or its processes or environment. The BAIP should provide a concise technical specification of the feature and a rationale for the feature. The BAIP author is responsible for building consensus within the community and documenting dissenting opinions.

BAIP Types
----------
There are three kinds of BAIP:

* A Standards Track BAIP describes any change that affects most or all Bitcoin Asset implementations, such as a change to the network protocol, a change in block or transaction validity rules, or any change or addition that affects the interoperability of applications using Bitcoin Asset.
* An Informational BAIP describes a Bitcoin Asset design issue, or provides general guidelines or information to the Bitcoin Asset community, but does not propose a new feature. Informational BAIPs do not necessarily represent a Bitcoin Asset community consensus or recommendation, so users and implementors are free to ignore Informational BAIPs or follow their advice.
* A Process BAIP describes a process surrounding Bitcoin Asset, or proposes a change to (or an event in) a process. Process BAIPs are like Standards Track BAIPs but apply to areas other than the Bitcoin Asset protocol itself. They may propose an implementation, but not to Bitcoin Asset codebase; they often require community consensus; unlike Informational BAIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Bitcoin Asset development. Any meta-BAIP is also considered a Process BAIP.


BAIP Work Flow
-------------

The BAIP process begins with a new idea for Bitcoin Asset. Each potential BAIP must have a champion -- someone who writes the BAIP using the style and format described below, shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea. The BAIP champion (a.k.a. Author) should first attempt to ascertain whether the idea is BAIP-able. 

Once the champion has asked the Bitcoin Asset community as to whether an idea has any chance of acceptance, a draft BAIP should be presented as a [pull request]. This draft must be written in BAIP style as described below.

It is highly recommended that a single BAIP contain a single key proposal or new idea. The more focused the BAIP, the more successful it tends to be. If in doubt, split your BAIP into several well-focused ones.

Authors MUST NOT self assign BAIP numbers, but should use an alias such as "baip-johndoe-infinitebitcoins" which includes the author's name/nick and the BAIP subject.

If the BAIP collaborators approve, the BAIP editor will assign the BAIP a number (generally the issue or PR number related to the BAIP), label it as Standards Track, Informational, or Process, give it status “Draft”, and add it to the git repository. The BAIP editor will not unreasonably deny an BAIP. Reasons for denying BAIP status include duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Bitcoin philosophy.

The BAIP author may update the Draft as necessary in the git repository. Updates to drafts may also be submitted by the author as pull requests.

Standards Track BAIPs consist of two parts, a design document and a reference implementation. The BAIP should be reviewed and accepted before a reference implementation is begun, unless a reference implementation will aid people in studying the BAIP. Standards Track BAIPs must include an implementation -- in the form of code, a patch, or a URL to same -- before it can be considered Final.

Once a BAIP has been accepted, the reference implementation must be completed. When the reference implementation is complete and accepted by the community, the status will be changed to "Final".

A BAIP can also be assigned status "Deferred". The BAIP author or editor can assign the BAIP this status when no progress is being made on the BAIP. Once a BAIP is deferred, the BAIP editor can re-assign it to draft status.

A BAIP can also be "Rejected". Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

BAIPs can also be superseded by a different BAIP, rendering the original obsolete. This is intended for Informational BAIPs, where version 2 of an API can replace version 1.

Some Informational and Process BAIPs may also have a status of "Active" if they are never meant to be completed. E.g. BAIP 001 (this BAIP).

What belongs in a successful BAIP?
---------------------------------

Each BAIP should have the following parts:

* Preamble -- RFC 822 style headers containing meta-data about the BAIP, including the BAIP number, a short descriptive title (limited to a maximum of 44 characters), the names, and optionally the contact info for each author, etc.

* Abstract -- a short (~200 word) description of the technical issue being addressed.

* Copyright/public domain -- Each BAIP must either be explicitly labelled as placed in the public domain (see this BAIP as an example) or licensed under the Open Publication License.

* Specification -- The technical specification should describe the syntax and semantics of any new feature. 

* Motivation -- The motivation is critical for BAIPs that want to change the Bitcoin Asset protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the BAIP solves. BAIP submissions without sufficient motivation may be rejected outright.

* Rationale -- The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

* The rationale should provide evidence of consensus within the community and discuss important objections or concerns raised during discussion.

* Backwards Compatibility -- All BAIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The BAIP must explain how the author proposes to deal with these incompatibilities. BAIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

* Reference Implementation -- The reference implementation must be completed before any BAIP is given status "Final", but it need not be completed before the BAIP is accepted. It is better to finish the specification and rationale first and reach consensus on it before writing code.

* The final implementation must include test code and documentation appropriate for the Bitcoin Asset protocol.

BAIP Formats and Templates
-------------------------

BAIPs should be written in mediawiki or markdown format.

BAIP Header Preamble
--------------------

Each BAIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.


 `BIP: <BAIP number>`
  `Title: <BAIP title>`
  `Author: <list of authors' real names and optionally, email addrs>`
  `* Discussions-To: <email address>`
  `Status: <Draft | Active | Accepted | Deferred | Rejected |
           Withdrawn | Final | Superseded>`
  `Type: <Standards Track | Informational | Process>`
  `Created: <date created on, in ISO 8601 (yyyy-mm-dd) format>`
  `* Post-History: <dates of postings to bitcoin mailing list>`
  `* Replaces: <BAIP number>`
  `* Superseded-By: <BAIP number>`
  `* Resolution: <url>`

Transferring BAIP Ownership
--------------------------

It occasionally becomes necessary to transfer ownership of BAIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred BAIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the BAIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the BAIP. We try to build consensus around a BAIP, but if that's not possible, you can always submit a competing BAIP.

If you are interested in assuming ownership of a BAIP, send a message asking to take over, addressed to both the original author and the BAIP editor. If the original author doesn't respond to email in a timely manner, the BAIP editor will make a unilateral decision (it's not like such decisions can't be reversed).

BAIP Editors
-----------

The current BAIP editor is Aleksey Karpov who can be contacted at [[mailto:admin@bitcoinasset.org]].

BAIP Editor Responsibilities & Workflow
--------------------------------------

For each new BAIP that comes in an editor does the following:

* Read the BAIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
* The title should accurately describe the content.
* Edit the BAIP for language (spelling, grammar, sentence structure, etc.), markup (for reST BAIPs), code style.

Once the BAIP is ready for the repository it should be submitted as a "pull request" to the [https://github.com/bitcoinasset/baip bitcoinasset/baip] repository on GitHub where it may get further feedback.


The BAIP editor will:

* Assign a BAIP number (almost always just the next available number, but sometimes it's a special/joke number, like 666 or 3141) in the pull request comments.

* Merge the pull request when the author is ready (allowing some time for further peer review).

* List the BAIP in [[README.md]]


The BAIP editors are intended to fulfill administrative and editorial responsibilities. The BAIP editors monitor BAIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

History
-------

This document was derived heavily from [Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [Python's PEP-0001]. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Bitcoin Asset Improvement Process, and should not be bothered with technical questions specific to Bitcoin Asset or the BAIP process. Please direct all comments to the BAIP editors.

Changelog
---------

22 September 2017 - Initial commit.

[markdown]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[README.md]: README.md "wikilink"
[Bitcoin's BIP-0001]: https://github.com/bitcoin/bips
[Python's PEP-0001]: https://www.python.org/dev/peps/
