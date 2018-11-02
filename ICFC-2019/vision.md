# Identify data replication challenges of always available/managed Edge clouds.

(See [glossary](./glossary.md))

Finally, we should propose a vision (and opportunity for the target audience) of
**tooling** that meets the outlined
[operational/consistency invariants](./chellanges.md) and that can help
implementing future data replicating systems for OpenStack and not limited to
(think of PaaS hosted on top, like Kubernetes). Therefore, that is also tooling
that should unify the systems design approaches for:

* Management plane (target audience: devops folks deploying and operating IaaS
  and PaaS on top)
* Control plane (for infrastructure owners and cloud or PaaS operators)
* PaaS on top of OpenStack, like OpenShift/Kubernetes (for tenants that deploy
  it over distributed fog cloud of clouds. Not sure, if there is the same
  data replication case for the tenants that only host workloads on PaaS, but
  having some KVS for Always-Available-Data-Store-as-a-Service in your
  OpenShift service catalog (Kubernetes Helm chart) may be a **very** good idea
  as well).

For example, we may end up proposing
[COPS](https://www.cs.cmu.edu/~dga/papers/cops-sosp2011.pdf), or RT-causal
implementations, if any do exist today. Or Global Galera Database, or StarlingX.
Or something custom based on version control systems and manual resolving for
conflicts, like git (not for binary data ofc). Whatever it may be, it should
bring the vision based on the wanted autonomy requirements and matching data
consistency model, not the implementation details yet.
