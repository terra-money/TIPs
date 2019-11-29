# Terra Improvement Proposals

Terra Improvement Proposals (TIPs) describe standards for the Terra platform, including core protocol specifications, client APIs, and contract standards.

A browsable version of all current and draft TIPs can be found on the official TIP site.

# Contributing

 1. Review [TIP-1](TIPS/tip-1.md).
 2. Fork the repository by clicking "Fork" in the top right.
 3. Add your TIP to your fork of the repository. There is a [template TIP here](tip-template.md).
 4. Submit a Pull Request to Terra's [TIPs repository](https://github.com/terra-project/TIPs).

Your first PR should be a first draft of the final TIP. It must meet the formatting criteria enforced by the build (largely, correct metadata in the header). An editor will manually review the first PR for a new TIP and assign it a number before merging it. Make sure you include a `discussions-to` header with the URL to a discussion forum or open GitHub issue where people can discuss the TIP as a whole.

If your TIP requires images, the image files should be included in a subdirectory of the `assets` folder for that TIP as follows: `assets/tip-N` (where **N** is to be replaced with the TIP number). When linking to an image in the TIP, use relative links such as `../assets/tip-1/image.png`.

When you believe your TIP is mature and ready to progress past the draft phase, you should do one of two things:

 - **For a Standards Track TIP of type Core**, ask to have your issue added to [the agenda of an upcoming All Core Devs meeting](https://github.com/ethereum/pm/issues), where it can be discussed for inclusion in a future hard fork. If implementers agree to include it, the TIP editors will update the state of your TIP to 'Accepted'.
 
 - **For all other TIPs**, open a PR changing the state of your TIP to 'Final'. An editor will review your draft and ask if anyone objects to its being finalised. If the editor decides there is no rough consensus - for instance, because contributors point out significant issues with the TIP - they may close the PR and request that you fix the issues in the draft before trying again.

# TIP Status Terms

* **Draft** - an TIP that is undergoing rapid iteration and changes.

* **Last Call** - an TIP that is done with its initial iteration and ready for review by a wide audience.

* **Accepted** - a core TIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author. The process for Core Devs to decide whether to encode an TIP into their clients as part of a hard fork is not part of the TIP process. If such a decision is made, the TIP will move to final.

* **Final (non-Core)** - an TIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author.

* **Final (Core)** - an TIP that the Core Devs have decided to implement and release in a future hard fork or has already been released in a hard fork. 

## Attribution

The TIP format and repository structure was adapted from Ethereum Improvement Proposals

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/)
