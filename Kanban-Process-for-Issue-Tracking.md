TriBITS uses a Kanban process with Github issue tracking using the GitHub Project [TriBITS](https://github.com/TriBITSPub/TriBITS/projects)

The Kanban stages are:

* **Backlog**: Every issue that gets created is automatically in the backlog 
* **ToDo**: Items a higher in the backlog that could be ready to work soon.
* **Selected**: Items scoped and ready to be worked next.
* **In Progress**: Issues we are actively being worked (or have already started to be worked even if they are stalled).
* **In Review**: Issues that are complete but need to be reviewed or are in review.
* **Done**: Issues have been completed and are providing real value to the customer.  (Closed issues without a 

When a new issue that is created, it is automatically put into "Backlog".

The intended Kanban process lifecycle is as follows:
* Someone creates a new Issue as a suggestion (and it automatically is placed in the Backlog).
* The Product Owner then takes the Issue and reviews it in the Backlog and comments on it (or closes it if justified).
* Regularly Issues are moved into "ToDo" or "Selected" when they are high enough priority and are ready to be worked.  (We should not cram a bunch of stuff into "Selected".  We should keep that list short so that it is clear what to work on next.)
* Where adequate capacity is freed up, an Issue is moved from "Selected" to "In Progress" by the developer and it is actively worked.
* Issues "In Progress" should be worked as quickly as possible to get them done.
* Once an Issue "In Progress" is ready, it is moved into "In Review" so it can be reviewed by someone.  (The code related to this issue should be submitted on a branch as a pull request to allow the review.)
* Once the Issue (and associated pull request) is independently reviewed, then the branch is merged and pushed (if the Issue is for a code change) and the Issue is closed.

That is the basic Kanban process in a nutshell.
