Pick needed terms from [Edge glossary](https://github.com/State-of-the-Edge/glossary)
and extend them for the missing openstack specifics needed for this paper.

* `deployment data` to: ...
  Examples: numbers of deployed computes, configuration
  pushed for openstack services, ansible inventory, tripleo deployment plan,
  hardware images for provisioning
* `cloud data` to: ...
  Examples: keystone users, glance images, ongoing RPC calls and DB transactions
* `control plane` to: ...
  Examples: openstack controller nodes, overcloud controllers (tripleo)
* `management plane` to: ...
  Examples: undercloud (tripleo), ansible control/admin node or Tower.
* Always available - operational mode that corresponds to the best of the
  [sticky available](https://jepsen.io/consistency/models/causal)
  data consistency models, which is either
  [Causal+ (COPS)](https://www.cs.cmu.edu/~dga/papers/cops-sosp2011.pdf), or
  [Real-Time Causal (RTC)](http://www.cs.cornell.edu/lorenzo/papers/cac-tr.pdf)
