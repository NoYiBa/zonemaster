## NAMESERVER03: Test availability of zone transfer (AXFR)

### Test case identifier
**NAMESERVER03** Test availability of zone transfer (AXFR)

### Objective

AXFR is a mechanism to transfer the whole content of a zone from a name
server. Some people prefer to not disclose the whole content of a zone
for various reasons, and thus wants the public name server infrastructure
not do disclose the whole zone content to the public. This test case
checks the availability of the AXFR mechanism.

AXFR is defined in its latest revision in
[RFC 5936](https://tools.ietf.org/html/rfc5936).

### Inputs

The domain name to be tested.

### Ordered description of steps to be taken to execute the test case

1. Find all hostnames for all the name servers used for the domain using
   [Method 2](../Methods.md#method-2-obtain-name-servers-from-parent) and
   [Method 3](../Methods.md#method-3-obtain-name-servers-from-child).
2. Send an AXFR query to each name server found in step 1.
3. If any answer to the AXFR query is starting with the SOA record
   for the domain, this test case fails.

### Outcome(s)

If any name server for the domain allows a zone transfer using AXFR,
this test case fails.

### Special procedural requirements

None.

### Intercase dependencies

None.

-------

Copyright (c) 2013, 2014, 2015, .SE (The Internet Infrastructure Foundation)  
Copyright (c) 2013, 2014, 2015, AFNIC  
Creative Commons Attribution 4.0 International License

You should have received a copy of the license along with this
work.  If not, see <http://creativecommons.org/licenses/by/4.0/>.
