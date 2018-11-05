> **NOTE**: Before we begin to format the paper, first write the content here
> and in the included files!

Items to expand and agree on:

* [abstract](./abstract.md) - Define the (tl;dr) scope for the position paper
* [glossary](./glossary.md) - Pick needed terms from [Edge glossary](https://github.com/State-of-the-Edge/glossary)
* [challenges](./challenges.md) - Identify data replication challenges of always available/managed Edge clouds
* [tooling](./vision.md) - Bring the vision and opportunity for tooling and system design approaches for target audiences

(Tl;dr) goals of that position paper:

* **position**: given Always Available autonomy support as a starting point,
  define invariants for both operational and data storage consistency
  requirements of control/management plane.

* **vision**: show that in the end that data synchronization and conflict
  resolving solution just boils down to having a causally
  consistent KVS (either causal+ or causal-RT, or lazy replication
  based, or anything like that), and cannot be achieved with *only*
  transactional distributed database, like Galera cluster. The way how
  to show that is an open question, we could refer to the existing
  papers (COPS, causal-RT, lazy replication et al) and claim they fit
  the defined invariants nicely, while transactional DB cannot fit it
  by design (it's consensus protocols require majority/quorums to
  operate and being always available for data put/write operations).
  We probably may omit proving that obvious thing formally? At least for
  the postion paper...

* **opportunity**: that is basically designing and implementing of such a
  causally-consistent KVS solution (see COPS library as example) for
  OpenStack, and ideally, unifying it for PaaS operators
  (OpenShift/Kubernetes) and tenants willing to host their containerized
  workloads on PaaS distributed over a Fog Cloud of Edge clouds and
  leverage its data synchronization and conflict resolving solution
  as-a-service.
