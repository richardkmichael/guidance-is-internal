## Question 5 FAQ

## Accounts

### We collaborate with a shared personal account. Can we use an Organization instead?

Absolutely!  Convert the shared User account to an Organization account,
and add your personal user accounts to Teams.  *Important:* You will not
be able to log in to the converted account after it is an Organization.
Be sure to add at least one of your personal accounts to the Owners team
during conversion.

Details are here:
https://help.github.com/articles/converting-a-user-into-an-organization

### We're new to GitHub, should we create a personal account then convert it to an Organization?

No. You can create an Organization as part of the sign up process or
later after you've all signed up.  Account conversion is primarily to
help people who _already_ collaborate using a shared single personal
account.

[TODO: Link.]

### Can I transfer the ownership of an Organization to a different user?

Yes.  Add the new account to the Owners Team, then use the new account
to remove your own account.

[TODO: Correct?  In Jan 2012, it was "contact support":
http://stackoverflow.com/questions/8736830/transfering-the-github-organization-ownership]

### I cannot log in using our Organization account.  What do I do now?

This is expected, an Organization account can not log in.  Instead, you
must log in with a personal account.

### How are Organizations different than Users?

Both have settings such as repositories, issues, and a billing plan.
However repository permissions are more flexible for organizations than
for users.

A User is a real human, either a repository owner or a collaborator.
Collaboration between user accounts always includes push privileges.

An Organization has Teams which group collaborators and repositories.
Each Team is assigned permissions on its repositories.  Team permissions
are flexible, and there is a pull-only permission.  Organizations have
unlimited private collaborators.

Details are here: 
https://help.github.com/articles/what-are-the-different-access-permissions

### Is an "Organization" different than an "Organization Account"?

Think of an Organization as a group owned "account", where the owners
each have a personal user account.  Organizations are implemented as a
special account type.  In practice, you do not need to worry about a
distinction, it is really just terminology.

### How do I switch Organization contexts?

After logging in, go to the [main page](http://github.com) then use the
drop down menu on the left.  The drop down menu appears on several
GitHub pages, including your dashboard at "http://github.com/dashboard".

[TODO: Screenshot.]

### Are Organizations available using the GitHub API?

Definitely! Be aware, because certain actions are only available to
Organization Owners, API requests must use authentication credentials
appropriate for the action.

## Teams

### How are Organizations and Teams related?

Teams belong to an Organization, and Organization Owners may create as
many as required.

### How are Teams and Repositories related?

Teams represent the permissions given to a group of collaborators on
specific repositories.  Team permissions are one of three levels,
ranging from full control to read only.  Please consult the Organization
Guide for details.

[TODO: Link.]

### Can Organizations allow pull only access to a repository?

Yes.  Add the user to a "Pull Team".  If you do not have such a team,
create one and then add the repository to the new team.

### Can I use a Team with a different Organization?  Can I transfer a Team?

No, teams belong to one a Organization and they cannot be transferred.
You will need to recreate the team in the other Organization.

## Repositories

### How are Organizations and Repositories related?

An Organization has repositories. It may have as many as your plan
permits.

### What happens when someone forks an Organization repo?

If the forker is a member of the Organization, the fork will remain
within the Organization.  It can be added to a Team, just as any other
Organization repository.  [TODO: Which team will own the fork?]

If the forker is *not* a member of the Organization, the fork will be
outside the control of your Organization.  It will behave just like any
other forked repostitory.

### How can I make commits to different Organizations use different
 email addresses?  For example, work and personal projects.

Add the different email addresses to your personal account, then adjust
the `git config` for each repository as necessary.  Use your global git
config to provide the most frequently used as the default.

For example, if you have more work repositories than personal ones, you
might use your work email address in your global git configuration.  On
the other hand, if you change work frequently, and do not want to forget
to change your global git config, use your personal email address in the
global git config and list your work address in the repository local git
config. 

### Can I define Team specific repository hooks?

No, hooks are property of repositories.

## Communication

### How can I subscribe to notifications for a group of our Organization's repositories?

Yes, you can do this with a team.  Create a team, add the repos which
interest you, then add yourself to the team.

### How can I keep up to date on Organization activity?

If you are in the Organization, change your context on the dashboard to
focus its News Feed, Pull Requests, and Issues.

If you are not in the Organization, you can follow any of Organization's
repositories or members.

### Can I follow an Organization or Team?

No. You must follow a User, or watch a specific repository.

#### Do Organization Owners receive notifications for the Organization's repositories?

No.  This is a difference between a User account and an Organization
account.  A User receives notifications for the repositories they own,
but Organization Owners do not receive notifications for all the
Organization's repositories.  Although suitable for a small
Organization, it would probably not be very useful for large ones.
