## Question 5 - An Organizations Guide

### A quick introduction: "Say ‘What?’ one more time!"

Organizations have repositories and Teams of users with specific
permissions on those repositories.  Teams can pull, push or pull, or
have full admin control over repositories, but not adjust the settings
of the Organization itself.  An Organization has unlimited private
collaborators, just add someone to a Team.

You may "context switch" GitHub's UI to a specific Organization,
limiting visible activity, issues, and pull requests so you can
concentrate on particular projects or "work".

Like all things GitHub, Organizations along with their Teams and members
are accessible via our API: http://developer.github.com/v3/orgs/

Organizations are free for open source.

Keep reading for usage and examples, or see the FAQ or knowledgebase
articles.

[TODO: move advantages here?  permissions / dashboard.]

### Nitty Gritty: "The same, but different."

An GitHub is account either a User account or an Organization account.

https://help.github.com/articles/what-s-the-difference-between-user-and-organization-accounts

Throughout this guide, "Organization" is used to mean "an Organization
account", just as "User" often refers to "a User account".  An
Organization account is similar to a User account, but there are
differences, discussed below in this guide.  A User account is for a
human, an Organization account is for a group.

A User account is required to use Organizations.

You may not have only an Organization account nor may you log in using
an Organization account.

Users can create an Organization, but an Organization cannot create
Users.

A User is _member of_ an Organization once they are a member of at least
one of the Organization's Teams.

If you are collaborating by sharing an existing User account, you can
convert that account to an Organization account.  Please see the FAQ.

### Overview

An Organization is similar to a User: it has repositories, a billing
plan, a profile and other settings.  Though unlike a User, an
Organization has Teams.

An Organization has Owners, who are have permission over the account
settings such as the billing plan, profile, etc.  In a sense, an
Organization account is a "group managed" account.

Organization Owners use Teams to finely control repository access: a
Team has a set of permissions with respect to specific repositories.
Permission types are discussed in detail below.  For example, an Owner
might create a restricted team with pull-only access to a repository.
Or, they could create a highly autonomous team with full admin control
over a repository.  A GitHub user is added to a Team, not to an
Organization.  Although, as a Team member they are also an Organization
member.

Organizations also provide a convenient way for you have a high level
view of everything happening around you.  Once you have membership in an
Organization through one of it’s teams, you can change the GitHub web UI
to show only activity related to a specific Organization.  For example,
you have an easily accessible view over all issues assigned to you
across all repositories.  Or, subscribe your RSS reader to the
Organization’s News Feed.

### Members: "The Inner Sanctum"

#### Adding and Removing

Organization members are all Users who are on it’s Teams.  Therefore,
when a User is added to a Team, they are automatically a member of the
Organization.

Users may not be *added* at the Organization level, adding must be done
through a Team.  However, to quickly remove a user from all Teams, they
may be *removed* at the Organization level.  Of course, a User may be
removed from only a specific Team.

#### Visibility

Visibility is handled at the Organization level.  Within an
Organization, members see each other’s membership: if you’re in, you
know everyone else who is in too.  Outside an Organization, memberships
may be hidden from the general public.

For example, member "Pointy Haired Boss" can’t hide from memeber "LOC
Writing Developer", but the "Security Audit Company" Organization might
add user "Whitehat Consultant" to a pull Team to perform a code audit
and conceal the membership from people outside the Organization.

### Teams: "Let’s play some DODGEBALL!"

#### Add and Removing

A Team is a collection of repository permissions applied to
collaborators.

Organization Owners may create or delete as many Teams as required,
there are no limits.  The Teams may have as many Users as required,
again, there are no limits - this includes private collaborators. 

When creating a team, you choose a team type: "Pull Only", "Push & Pull"
or "Push, Pull and Administrative"; then add member users and
repositories.

There is one additional team type: the "Owners Team".  It is not
possible to create another Owners Team, _there may be only one_.  To
manage Organization administrators, add or remove people from the Owners
Team.

*Important:* Teams are specific to an Organization and are not shared
 between different Organizations.

https://help.github.com/articles/how-do-i-set-up-a-team 

#### Permissions

Grouping an Organization’s members into Teams allows fine grained
repository access control but maintains flexible collaboration among
everyone.

The Team types have a permissions hierarchy, so that each level-up
permits the action of the team below it.  The details of the permissions
granted to each Team type, are available here:
https://help.github.com/articles/what-are-the-different-access-permissions

The "Owners Team" has the highest permission level.  Owners Team members
have access to all team functions and repositories.  In addition, they
may edit the Organization settings such as the profile, billing
information, or account deletion.

A "Push, Pull and Administrative" team has control over repositories
within their own Team, including creation, deletion, and transfer in or
out of the Organization.  They can do anything an owner can do.

A "Push & Pull" team may write to repositories within their own Team,
and may also manage issues, pull requests, and comments; apply labels;
and create milestones.  This team type corresponds to the permissions
given to Collaborators on personal user account owned repositories.

A "Pull" team is the most restricted team, members are only able to read
the repositories within their team.  Members on these teams may also
edit wikis, open issues and edit their own comments.

#### Communication

To talk to an entire team, use "@organization/teamname" in any GitHub
comment, just as a normal user mention.

### Repositories: "With great power..."

#### Ownership

Repositories are owned by the Organization, not by a Team.  A team is
_given access_ to a repository by adding it to the team.  A repository
may be assigned to many teams, and access is controlled based on the
permission level of the team type.

Note that "Push, Pull and Administrative" teams have complete control
over their repositories, include the ability to delete.

#### Creation

Organization Owners may create new respositories and assign them to
Teams.  Administrative Teams may create new repositories which are
automatically added to their Team.  [TODO: Why does this make sense?
I'm on an Admin Team, I create a repo, how can I give other people
access to it?  I can't control other teams, e.g. a read-only team.] 

#### Forks

When an Organization member forks an Organization repository, the fork
remains in the Organization. [TODO: In which team?]

When an Organization Owner or Admin Team member forks any repository,
the fork can be created in the Organization instead of in their personal
account.

[TODO: What happens when a non-Organization member forks an Organization
repository?  Ex. Fork Organization to Organization?]

#### Notifications

Team members receive notifications for their Team's repositories.

*Important:* Organization Owners *do not* receive notifications for all
 repositories in the Organization.  This is in contrast to a User
receiving notifications for all their repositories.

### Organization Account Settings

Similar to a User's "Account Settings", an Organization has a billing
plan, repository ownership, and profile.  These are only available to
the Owners Team.  To grant access to a user, add them to the Owners
Team.  As a reminder, there may be only one Owners Team, to which users
may be added or removed.

### Examples: "How can Organizations help us?"

#### Collaborate for the win!

* A "VisiCalc Testers" pull team could be used to give read access to
  their repositories, while ensuring testers need to fork and
  pull-request any changes.

* An Organization might have several Admin Teams, one "Marketing
  Materials Admins" who control the repositories of all the marketing
  related projects, and another "Skunkworks Admins" who control the
  repositories of super-top-sekret projects.

* "Global Chemical Unlimited" Organization often works with external
  contractors, but the contractors change.  The Organization Owners
  create two "Push & Pull" teams: "GCU Developers" and "Guns For Hire
  Contractors" and give both teams access to the same repositories.
  However, new contractors are added to the "Guns For Hire" team.  When
  enough Happy Fun Balls have been sold and the company has strong
  internal development team, they stop contracting and delete the "Guns
  For Hire" team without disrupting access for their internal developers.

#### Get things done

* While logged in to GitHub, your session is in the context of an
  Organization.  The dashboard will display the News Feed, Pull
  Requests, Issues and Teams for the current Organization context.  This
  gives a focused view of the Organization's activity.  For example, use a
  company Organization during the work day, then change to an open source
  project organization in the evening.

### Additional Reading

#### GitHub materials

https://github.com/path/to/new/faq [Organizations FAQ]
https://github.com/blog/674-introducing-organizations [Introduction]
https://help.github.com/categories/2/articles [All Organization articles]
https://github.com/features/projects [Manage teams with Organizations]
https://groups.google.com/d/msg/github/l1_r30VyHF0/uAjvEOnJjbQJ [Team notifications]
https://groups.google.com/d/msg/github/Y3MXIbigCBc/EJATR5OuV6AJ [Teams v. Collaborators v. Accounts]

#### Other resources

* GitHub Google Group
* StackOverflow
