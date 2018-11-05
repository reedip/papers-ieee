Edge clouds control plane and management data consistency challenges
====================================================================

Fog computing is emerging Cloud of (Edge) Clouds technology. Its control plane
and deployments data synchronization is a major challenge. Autonomy requirements
expect even the most distant edge sites always manageable, available for
monitoring and alerting, scaling up/down, upgrading and applying security fixes.
Whenever temporary disconnected sites are managed locally or centrally, some
changes and data need to be eventually synchronized back to the central site(s)
with having its merge-conflicts resolved for the central data hub(s). While
some data needs to be pushed from the central site(s) to the Edge, which might
require resolving data collisions at the remote sites as well. In this paper,
we position the outstanding data synchronization problems for OpenStack
platform becoming a cloud solution number one for fog computing. We define the
inter-cloud operational invariants based on that Always Available autonomy
requirement. We show that a causally consistent key value storage is the best
match for the outlined operational invariants and there is a great opportunity
for designing such a solution for Edge clouds. Finally, the paper brings the
vision of unified tooling to solve the data synchronization problems the same
way for infrastructure owners, IaaS cloud operators and tenants running
workloads for PaaS, like OpenShift or Kubernetes deployed on top of Edge
clouds.
