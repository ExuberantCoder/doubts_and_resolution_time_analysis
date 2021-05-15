# doubts_and_resolution_time_analysis

Quick brief on how the doubt resolution works:
1. As part of their learning journey, a student can raise a doubt while going through any
type of content.
2. Their doubts are resolved by our Teaching Assistants(TA) who can see the doubts on
a portal and once assigned, resolve them via 1-on-1 chat with the student.
3. As soon as a doubt is raised, it goes to the pool of open doubts and the status is
marked as available.
4. When a TA is online, we assign them a single doubt to work on and the status
changes to assigned.
5. TA can choose to reject or accept the doubt. In case they don’t take any action, it is
automatically unassigned and is moved to the available state.
6. In case the TA accepts the doubt, it goes to the active state.
7. Once in the active state, TA can either mark it as resolved or mark it as pending on
user if they want some additional info from the user. They can also leave the doubt
midway, in that case it becomes available again.
8. In case the TA marks the doubt resolved, it goes to status of
resolved_review_pending, which means that we wait for the user to confirm that the
doubt is actually resolved.
9. In case of pending on the user, the user can mark it resolved or they can provide the
required information and again make it available.
10. Post the doubt is resolved, the user gives a rating out of 5 (1-worst, 5-best) on the
experience.


Definitions
1. Doubt Activity: Every time either the user, TA or the system does an activity we
create an entry in the Doubt Activity table. All the fields are self explanatory for the
table except the user_id:
a. User_id contains the id of the action taker for that activity e.g. user_id would
represent the id of the student in case of the following activities: resolve, rate,
review_not_resolved, not_pending_action_done, not_pending_info_submit
b. User_id will be the id of the TA in case of following: activate, reject,
pending_action_required, pending_information_required,
review_resolution,assign, accept,reactivate, escalate
c. It would be a System user id in case of unassign, inactivate, pending_sms,
pending_reminder_first, pending_reminder_second, dead
2. Doubt Resolution Time: We calculate this by subtracting the doubt creation time
from time of ‘resolve’ activity on the doubt.

Task: We would recommend you to play around with the data. You can either work on it in
excel or upload the data into a db and then use sql on it. We would like you to do the
following analysis and share the final report along with the excel/sql queries which you used
for the analysis.

1. Overall analysis around the resolution time
2. An analysis on the effect of Resolution time on the user rating
3. How many doubts are resolved by each TA?
4. Our performance in doubt resolution in different courses.
5. Any other suggestions from your side.
