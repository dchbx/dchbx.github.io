# Affordable Care api (ACapi)

The ACapi is conceived to support the DC Health Benefits Exchange (DCHBX).  Understanding the value of the framework, the services, and models built into the ACapi made way for the concept of an OpenHBX – where functional aspects, in whole or in subsets, could be plugged into other exchanges.

## Important Information

This area will be updated periodically so regular visitors to the site will have updated information.  The information might be critical or just informative.

## Documentation Resources

| Component | Description |
| --------- | ----------- |
| DCHBX Website | Main site for the DC Health Benefit Exchange Authority (http://www.dchbx.com/) |
| GitHub Project Site | GitHub site for DCHBX (https://www.github.com/dchbx/) – information and repository for packages |
| Canonical Vocabulary | A complete XSD vocabulary and data contract for ACapi Resource Operations and Events |
| ACapi                | Resource Operations, Resource Events, and Common Services API. |
| Common Services      | Common services supporting the API and Resource Operations and Events. |
| Governance and Rules | Requirements, constraints, and policies to use the ACapi and Common Services. |
| Transport            | DCHBX ACapi Bridge and Message Oriented Middleware (MOM) layer. |
| Security             | Layer security implemented to secure data in the HBX. |

## For Developers

The ACapi and OpenHBX has documented the API offered for developers to give client systems and user systems access to Resources, the Operation Model, and the Event Model.

## Getting Started

The ACapi is a packaged and pluggable backbone to Health Benefit Exchange.  It could be used exclusively to back-end a complete Health Benefits Exchange or components and packages of the ACapi could augment existing Health Benefit Exchange functionality to implement areas needing realization or implementation.

### System Requirements

System requirements are being compiled for users and implementors outside of the DCHBX for OpenHBX application.  

### Installation and Packaging

ACapi is comprised of these packages:

| Package       | Description |
| -------       | ----------- |
| cv            | Canonical Vocabulary - Contract with HBX Resource Operations and Events |
| gluedb        | Glue Database - Exchange Ops |
| hbx_edi       | EDI Transaction - Interface with Carriers |
| hbx_transport | OpenHBX Transport – Bridge between clients, users, and MOM |
| hbx_console   | UI package to manage HBX settings |

### License

ACapi and OpenHBX by [District of Columbia Health Benefit Authority](https://dchealthlink.com/) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).
