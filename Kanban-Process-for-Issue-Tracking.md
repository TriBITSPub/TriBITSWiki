Here we are using a simple Kanban process with Github issue tracking.  Inspiration for this comes from [this blog article](http://www.ianbicking.org/blog/2014/03/use-github-issues-to-organize-a-project.html).  A great into and howto for Kanban is [Kanban vs. Scrum - making the most of both](http://www.infoq.com/minibooks/kanban-scrum-minibook).

We are using "Milestones" as the different Kanban stages:

* [1_backlog](https://github.com/TriBITSPub/TriBITS/milestones/1_backlog) : Issues we will do some day hopefully
* [2_selected](https://github.com/TriBITSPub/TriBITS/milestones/2_selected) : Issues we will do next once we have enough free capacity [Limited to 4 items]
* [3_in_progress](https://github.com/TriBITSPub/TriBITS/milestones/3_in_progress): Issues we are actively working one [Limited to 4 items]
* [4_in_review](https://github.com/TriBITSPub/TriBITS/milestones/4_in_review): Issues that are complete but need to be reviewed or are in review [Limited to 4 items]
* [5_ready_to_deploy](https://github.com/TriBITSPub/TriBITS/milestones/5_ready_to_deploy): Issues that are complete and reviewed but have not been deployed to the customer yet.
* [6_deployed](https://github.com/TriBITSPub/TriBITS/issues?utf8=%E2%9C%93&q=is%3Aclosed): Issues have been completed and are providing real value to the customer.

A new issue that is created is in limbo until it is moved into either 1_backlog, 2_selected, or 3_in_progress.  An issue is not acknowledged until it is assigned to one of these "milestone" categories.

The intended Kanban process lifecycle is as follows:
* Someone creates a new Issue as a suggestion
* The Product Owner then takes the Issue and assigns it to 1_backlog
* Regularly Issues are moved into 2_selected when they are high enough priority and are ready to be worked.  But we don't just cram a bunch of stuff into 2_selected.  We keep that list short so that it is clear what to work next.
* Where adequate capacity is freed up, an Issue from 2_selected is moved into 3_in_progress and is actively worked.
* Issues in progress (3_in_progress) should be worked as quickly as possible to get them done.
* Once an Issue is ready, it is moved into 4_in_review so it can be reviewed by someone.  Typically a branch would be pushed and referenced in the Issue ticket.
* Once the Issue is independently reviewed, then the branch is merged and pushed (if the Issue is for a code change) and the Issue can either be moved to 6_deployed and closed, or it is moved to 5_ready_to_deploy if the customer has not accepted the update yet.
* For Issues stuck in 5_ready_to_deploy, once the customer takes possession of the change and is benefiting from the work done in the Issue, then the Issue can be moved to 6_deployed and closed.

That is the basic Kanban process in a nutshell.

NOTES:
* An issue that is closed without being assigned to any of the Kanban stages (i.e. 6_deployed) is rejected and will not be developed.
