See [Nifi mailing list thread](http://apache-nifi-users-list.2361937.n4.nabble.com/PutTCP-connector-not-cleaning-up-dangling-connections-td2912i20.html)


Verification for [NIFI-4391](https://issues.apache.org/jira/browse/NIFI-4391)

- Built Nifi 1.4.0-SNAPSHOT + your PR and used that as my base nifi installation 
- Noticed weird characters in the tcp responses 
- Switched to 1.3.0. No more weird characters 
- Isolated the PutTCP processor by creating a custom PutTCP (see github repo below) to experiment (instead of the built-in PutTCP) 

The Repo has 2 branches. 

- master contains an "older" PutTCP processor from the Nifi code base. With that one I don't have the weird characters (even on a nifi 1.4.0-SNAPSHOT + your PR). 
- If I use the dev_puttcp_1.4 branch on my nifi I get the weird characters. 