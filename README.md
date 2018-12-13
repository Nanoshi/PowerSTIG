# Power STIG
Powershell tools to manage an manipulate STIGs, SCAP scans, XCCDFs, and CLKs

STIG - Refers to the full manual 


## Work flows and scrpits to run

- Download all STIGs and Benchmarks (manually)

## History of STIGs and SCAP according to u/m00f

A very abbreviated history, hopefully I get most of this right.

First there was CVE. The US Government (via NIST and Mitre) created CVE so that vendors could have a common ID for talking about a vulnerability. Overtime, vendors started using CVE instead of BugTraq and other proprietary IDs.

Then there was FISMA: a US law that required the US government to secure their computers. Everything was manual and audits took years.

Then there was OVAL. Let by NIST and Mitre and vendors, they came up with a way to describe vulnerabilities in XML so that vendors and government could have a common format to define a vulnerability so that vendors and open source people could automate around this standard.

At this point the gang at NIST and Mitre had a vision and momentum for defining IDs and standards around computer security.

We are now in 2007-ish. Millions of man-hours are wasted doing FISMA compliance. Directed by the OMB, NIST is tasked with finding a way to automate all of this. They create SCAP, which uses OVAL to describe configuration compliance conditions (since a vuln definition and a configuration compliance definition are really quite similar), they use CCE to ID the checks (just like CVE IDs a vuln), and they use XCCDF to create a list of checks, aka a checklist or benchmark. They use CPE as an ID for apps and OSes.

SCAP is just a name for the combination of: OVAL (for compliance checks, not vulns), CCE, XCCDF, CPE. Of course, SCAP is an actual standard written by NIST with the intention of certifying vendors who are compliant with it. And, despite being a pretty poorly run program, many vendors go through the painful process of getting certified (e.g. McAfee, Symantec, Tripwire, etc).

CIS then starts converting all of their checklists to "SCAP" (meaning OVAL and XCCDF). The DoD starts doing this too with the DISA STIG checklists. So, today, there are now a ton of OS and application security checklists that are "SCAP checklists".

Now, the funny thing about SCAP validation is that it is not just a protocol for defining how a checklists is created by also blends in the requirement that specific checklists (like the FDCC and USGCB checklists) be correctly executed to become certified. The reason for this is that SCAP was created to help US Government agencies pass FISMA compliance, so there has to be some sort of standard for measuring that compliance.
