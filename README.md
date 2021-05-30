![TIPS-banner](./img/TIPs_banner.png)

This repository houses the official working and finalized drafts for Terra Improvement Proposals (TIPs), which describe standards for the Terra platform, such as developments in the specification of the core protocol, application protocols, informational drafts, and contract standards.

The [official TIPs site](https://tips.terra.money) is automatically generated from the contents of this repository.

# Contributing

1.  Review [TIP-1](./tips/tip-1/README.md).
2.  Fork the repository by clicking "Fork" in the top right.
3.  Add your TIP to your fork of the repository. There is a [template TIP here](./tips/tip-x/README.md).
4.  Submit a Pull Request to Terra's [TIPs repository](https://github.com/terra-money/TIPs).

Your first PR should be a first draft of the final TIP. It must meet the formatting criteria enforced by the build (largely, correct metadata in the header). An editor will manually review the first PR for a new TIP and assign it a number before merging it. Make sure you include a `Agora` header with the Terra Agora URL to a discussion forum or open GitHub issue where people can discuss the TIP as a whole.

Each TIP has its own designated folder which is owned by the TIP's author. If your TIP requires images, you should put the image files directly in the TIP's folder, e.g. `tips/tip-xxxx/img/image.png`, and the image files should be referenced relatively from within `tips/tip-xxxx/README.md` as `.img/image.png`.

When you believe your TIP is mature and ready to progress past the draft phase, you should do one of two things:

- **For a Standards Track TIP**, ask to have your issue added to the agenda of Terra Core Developer meetings (https://github.com/terra-money/core/issues), where it can be discussed for inclusion in a future hard fork. If implementers agree to include it, the TIP editors will update the state of your TIP to `Accepted`.

- **For all other TIPs**, open a PR changing the state of your TIP to `Final`. An editor will review your draft and ask if anyone objects to its being finalized. If the editor decides there is no rough consensus - for instance, because contributors point out significant issues with the TIP - they may close the PR and request that you fix the issues in the draft before trying again.

## Attribution

The TIP format and repository structure was adapted from Ethereum Improvement Proposals.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/)
