# Omni-AI Enhancement Proposals (OEPs)

A Omni-AI Enhancement Proposal (OEP) is a way to propose, communicate and coordinate on new efforts for the Omni-AI community project. The OEP guidelines adopted here is heavily
influenced by the [Kubernetes Enhancement Proposals](https://github.com/kubernetes/enhancements/blob/master/keps/README.md) (KEPs) designed by Kubernetes community.

**NOTICE:** *For similar structures some of the same wordings from KEPs are borrowed to adhere to the originally construed meaning.*

## Quick start for the OEP process

1. Socialize an idea with a sponsoring SIG.
   Make sure that others think the work is worth taking up and will help review the OEP and any code changes required.
2. Follow the process outlined in the [OEP template](XXX-oep-template/README.md).

## FAQs

### Do I have to use the OEP process?

More or less, yes.

Having a rich set of OEPs in one place will make it easier for people to track
what is going in the community and find a structured historical record.

OEPs are required for most non-trivial changes. Specifically:
* Anything that may be controversial
* Most new features (except the very smallest)
* Major changes to existing features
* Changes that are wide ranging or impact most of the project

Beyond these, it is up to each SIG to decide when they want to use the OEP
process. It should be light-weight enough that MEPs are the default position.

### Why would I want to use the OEP process?

Our aim with OEPs is to clearly communicate new efforts to the MindSpore contributor community.
As such, we want to build a well curated set of clear proposals in a common format with useful metadata.

Benefits to OEP users (in the limit):
* Cross indexing of OEPs so that users can find connections and the current status of any MEP.
* A clear process with approvers and reviewers for making decisions. This will lead to more structured decisions that stick as there is a discoverable record around the decisions.

We are inspired by Kubernetes KEPs, IETF RFCs, Python PEPs and Rust RFCs.

### Do I put my OEP in the root OEP directory or a SIG subdirectory?

Almost all OEPs should go into SIG subdirectories. In very rare cases, such as
OEPs about OEPs, we may choose to keep them in the root.

### What will it take for OEPs to "graduate" out of "beta"?

Things we'd like to see happen to consider OEPs well on their way:
* A set of OEPs that show healthy process around describing an effort and recording decisions in a reasonable amount of time.
* Presubmit checks for OEPs around metadata format and markdown validity.

Even so, the process can evolve. As we find new techniques we can improve our processes.

### What is the number at the beginning of the OEP name?

OEPs are now prefixed with their creation time (eg. yyyy-mm-dd). This gives
both the OEP a unique identifier and provides an easy breadcrumb for people to
find the issue where the current state of the OEP is being updated.
