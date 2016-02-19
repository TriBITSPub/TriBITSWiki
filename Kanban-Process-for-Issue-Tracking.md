TriBITS uses a Kanban process with Github issue tracking with the tool [waffle.io](https://waffle.io/TriBITSPub/TriBITS).

The Kanban stages are:

* **Backlog**: Issues we will do some day hopefully
* **Ready**: Issues we will do next once we have enough free capacity [Soft limit of 4 items]
* **In Progress**: Issues we are actively working one [Soft limit of 4 items]
* **In Review**: Issues that are complete but need to be reviewed or are in review [Soft limit of 4 items]
* **Done**: Issues have been completed and are providing real value to the customer.

See [TriBITS Kanban Board](https://waffle.io/TriBITSPub/TriBITS).

When a new issue that is created, it is automatically put into "Backlog".

The intended Kanban process lifecycle is as follows:
* Someone creates a new Issue as a suggestion (and it automatically is placed in the Backlog).
* The Product Owner then takes the Issue and reviews it in the Backlog and comments on it (or closes it if justified).
* Regularly Issues are moved into Ready when they are high enough priority and are ready to be worked.  But we don't just cram a bunch of stuff into Ready.  We keep that list short so that it is clear what to work on next.
* Where adequate capacity is freed up, an Issue from Ready is moved into In Progress by the developer and is actively worked.
* Issues In Progress should be worked as quickly as possible to get them done.
* Once an Issue is ready, it is moved into In Review so it can be reviewed by someone.  The code related to this issue should be submitted on a branch as a pull request to allow the review.
* Once the Issue (and associated pull request) is independently reviewed, then the branch is merged and pushed (if the Issue is for a code change) and the Issue is closed.

That is the basic Kanban process in a nutshell.
