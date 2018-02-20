# Business Group Document Management

![guld](gap://media/image/guld/guld-logo-set-without-background/6_guld_ gold_logo_no_name.png)

Author: [Ira Miller](gap://life/isysd) &lt;[public@iramiller.com](mailto:public@iramiller.com)&gt; [iramiller.com](https://iramiller.com)

### Problem

Business groups face a number of challenges at the juncture of IT and legal. If proper steps are not taken to capture and store every step of contract execution, the consequences can be loss of business, bloated operations, negligence, fraud, or even embezzlement.

### Solution

The lifecycle of a contract is request, writing, discussion, execution, and finally storage. By utilizing [git](https://en.wikipedia.org/wiki/Git), a revision control file system, for all legal documents, each of these steps can be recorded perfectly, including meta-data like author(s), signer(s), timestamps, and even supporting identification for counter-parties, such as corporate email server signatures. Additionally, the shared cloud-storage functionality of git will improve workflows, reducing confusion over document version, and email chains.

Basically, the group can have a private dropbox, where every change to every document is perfectly recorded, even if it was made by a third party.

### Technical Details

[Git](https://git-scm.com), well known through hosting service [github](http://github.com/), is used by every major company and institution in the world, from the US Department of Defense to Google. It is free, open source, and supported for every computer language and operating system.

Though trustworthy companies like github offer enterprise hosting services, it is trivial for an enterprise IT department to run their own [git server](https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server). The author would recommend [gitolite](http://gitolite.org/) to simplify management of a large number of users.

##### User Experience

Seamless desktop integration is possible with git, so that a local directory can be synchronized with the group. After setup, this should not require any action on the part of the user, making the solution suitable for anyone from a new secretary to a senior partner.

Anyone who has used [Dropbox](https://www.dropbox.com) or [Google Drive](http://drive.google.com) to share a local folder will be able to use this cloud drive.

##### Contract lifecycle

The contract lifecycle with our git cloud server looks like each person opening and saving the file in order, until the final person prints and physically signs the paper version. Because each time the file is opened and saved, the digital signature of the user is recorded, no further action is strictly necessary to indicate review and approval of the contract. As a visual signal, typing in your name would be appropriate.

![Lifecycle Flowchart](gap://media/image/isysd/business-group/Contract-lifecycle.jpg)

##### Users and Teams

Users can be organized into teams with group or individual permissions. [Gitolite](http://gitolite.org/) allows this sort of configuration in a clear and secure manner.

In the context of a business group, it is recommended to create one or more repository (shared folder) per company, and reflect corporate structure in the user permissions. For those familiar with [Fork/PR workflow](https://gist.github.com/Chaser324/ce0505fbed06b947d962), the goal is to have the managers and business executives to merge changes into the organization's master records from topic-based, working forks.

##### Security

Though git servers can identify users by open standards like [SSH keys](https://www.ssh.com/ssh/protocol/), the author also recommends having each user generate a [PGP key](http://openpgp.org/) to use for signing all file changes. This leaves a stronger trail of ownership, since PGP signatures are stored in the git database, while SSH signatures are discarded after server authentication. Each user device can be configured to perform these signatures in the background upon file save.

PGP can also be used to encrypt files, for extra security. This could be useful for corporate secrets that should not be known by employees, including IT personnel. In fact, such encryption is the only way to keep a secret from IT personnel.

### Implementation steps

To put this plan into action, take the following steps.

1. Set up a gitolite server for the group, preferably with backups.
2. Install git, a git UI on all workstations.
3. Generate SSH and PGP keys for each user and install on respective workstations.
4. Create git repositories, users, and groups to map to corporate structure.
5. Train employees on use of their new cloud storage system.
