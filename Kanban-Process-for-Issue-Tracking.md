# Kanban process for Issue Tracking

Here we are using a simple Kanban process with Github issue tracking.  Inspiration for this comes from [this blog article](http://www.ianbicking.org/blog/2014/03/use-github-issues-to-organize-a-project.html).  A great into and howto for Kanban is [Kanban vs. Scrum - making the most of both](http://www.infoq.com/minibooks/kanban-scrum-minibook).

We are using "Milestones" as the different Kanban stages:

* 1_backlog : Issues we will do some day hopefully
* 2_selected : Issues we will do next once we have capacity [Limited to 4 items]
* 3_in_progress: Issues we are actively working one [Limited to 4 items]
* 4_in_review: Issues that are complete but need to be review or are in review [Limited to 4 items]
* 5_ready_to_deploy: Issues that are complete and reviewed but have not been deployed to the customer yet.

A new issue that is created is in limbo until it is moved into either 1_backlog, 2_selected, or 3_in_progress.  An issue is not acknowledged until it is assigned to one of these.

An issue that is closed without being assigned to any of the Kanban stages is rejected and will not be developed.

 






