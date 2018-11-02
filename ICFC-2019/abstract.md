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
we position the outstanding data synchronization problems for OpenStack cloud
platform becoming a solution number one for fog computing. We outline the data
consistency requirements and design approaches to meet the AA (Always
Available) autonomy expectations. Finally, the paper brings the vision of
unified tooling, which solves the data synchronization problems the same way
for infrastructure owners, IaaS cloud operators and tenants running  workloads
for PaaS like OpenShift or Kubernetes deployed on top of  OpenStack. The
secondary goal of this work is to help cloud architects and developers to
federate stateful cloud components over reliable distributed data backends and
having its failure modes known.
