# Identify data replication challenges of always available/managed Edge clouds.

(See [glossary](./glossary.md))

The goal is to name the current blockers making the system design invariants
below a True Challenge.

It is assumed that edge sites global autonomy requirement is: deployment data
for management plane, and cloud data for control plane of Edge clouds must meet
the consistency requirements allowing the end system to operate as
Always Available. From the operational point that is:

* OpenStack cloud objects, like users, images or VM instances, can always
  be CRUD'ed via available APIs/CLI, either via the central control hubs or
  locally at the remote edge sites. If remote sites are not available, the
  pending operations should be queued for the future application and conflicts
  resolving.
* Local cloud operations can be processed (limited to the remote site control
  plane locality) without waiting for the central control plane.
* Similarly the to control plane operations, deployed cloud infrastructure nodes
  can always be scaled up/down by the central or local management planes, via
  updating the required deployment data and rolling required actions over
  available APIs/CLIs. Same queueing capabilities shall apply.
* Security patches/kernel upgrades can always be installed by the same meanings
  (locally or queued from the central hubs).
* Major versions of system components, like OpenStack itself, can be always
  upgraded (locally or queued from the central hubs).
* Queued actions can eventually catch up with its remote targets, if possible,
  or be expired by some policies, or may be discarded by the conflicts merger.
* There is a full view from the central hub(s) into the Cloud of Edge Clouds for
  the key administrative aspects, like hardware status (installed OS images, power
  management et al), systems state monitoring and alerting.

> **NOTE**: The caveat is that things like "global view", central or local states
> may be not always current, given the eventual nature of operations. Expiration,
> priorities, conflicts resolving rules (data precedence) for the local vs central
> hubs' data is the subject for future design and will not be covered in this position
> paper. But these definitly pose a problem that must be mentioned as a challenge here.

And from the data point, Always Available is:

* Data can be modified at any given moment of time, despite of inter-sites
  network connectivity, and there is no limitations, like read only access modes.
  this affects all central and remote data hubs' local management/control state.
* Data can be synchronized eventually across central and remote hubs, with
  conflicts auto-resolved, or stored somewhere for later processing, like by hand
  (think of git merge conflicts).

> **NOTE**: some limitations and additional constraints do exist though for the
> sticky available [consistency models](https://jepsen.io/consistency) and its
> the best options causal+ and RTC.

Additionally, we need to expand on the challenges, like conflicts resolving,
data precedence for it, queueing of operations that cannot complete because of
the disconnected remote sites and expiration policies for those operations.
Invalidating of the cached state, like glance/ironic images downloaded from central
hubs to remote edge sites fits into this area as well.
