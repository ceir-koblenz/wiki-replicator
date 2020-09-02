# Wiki Replicator

This application replicates wikis from a connection plattform and stores them in an nsf for offline use. It was developed by Jonas Baier for CEIR in an endeavor to have access to the content of important wikis during downtimes of the connections platform.

# Installation

Clone the repository and associate the On-Disk Project with a newly created nsf or simply use the compiled nsf. Remember to create a working directory for the application.

# Domino Server

It is recommended to all users to replicate the application for offline use when the server is down.

It is best practice to create an user account for the application and make it a member of all the wikis that should be replicated. In this case you do not have to enter the credentials of a real user and you can use the agent with more features.

### ACL

If your Connections platform uses your Domino LDAP you can make use of the "Access restriction" feature:
Give the administrators manager access and all other users reader access to the application and the Wiki Replicator will synchronize the access to the wikis.



# Notes Client

**Note: replication process will take much longer.**

Simply input your connections credentials into your configuration document. To increase performance just disable access restriction as it has no effects when used by a single client. To further decrease download times you may want to disable the download of attachments although this comes with a drawback.

You may also want to disable the scheduled agent runs entirely in the Designer and trigger them manually.

# Agents

The application includes two agents:

***"getWikis"***

This agent checks for the wikis to be replicated on every run and has the ability to restrict user access. It is the recommended agent and scheduled by default.

***"getWikiContent"***

This agent only updates the content of the wikis already present in the application. To use this agent you firstly have to trigger the other agent and delete the unwanted wikis afterwards. You will have to repeat this procedure everytime you want to update the wikis to be replicated.
This agent is recommended if you do not have an exclusive user account for the application.
