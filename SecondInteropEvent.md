# Goal #
The usual.  Bang up as many implementations as we can.  Primarily this should find weaknesses in the implementations and - more importantly - the spec.

IIW has a demo hour after lunch on Wednesday.  This is a great opportunity to show interoperability and spread the word about SCIM through working code.  After the demo hour, participants can dive deeper into more use cases.


# When & Where #

[IIW (May 1-3/2012) in Mt View, CA](http://www.internetidentityworkshop.com/)

Wednesday May 2, 2012 - 12:00-4:00pm PDT (proposed)

**Schedule:**
  * 12-1 - Setup to be able to show demonstrable interoperability
  * 1-2 - Demo hour
  * 2-4 - Deeper interoperability testing against use cases

Remote participation will be available if the participant has a public server endpoint.


# Who #

| Person | Representing | Client | Server | Auth | Download/Endpoint |
|:-------|:-------------|:-------|:-------|:-----|:------------------|
| Trey Drake | [UnboundID](http://www.unboundid.com) | Y      | Y      | Server Basic only, Client Basic and OAuth | http://code.google.com/p/scimsdk/ |
| Kelly Grizzle | [SailPoint](http://www.sailpoint.com) | Y      | N      | Basic/OAuth |                   |
| Erik Wahlström  | [Technology Nexus - ScimProxy](http://www.nexussafe.com) | Y      | Y      | Basic/OAuth | http://code.google.com/p/scimproxy/ |
| Samuel Erdtman | [Technology Nexus - PortWise Access Manager](http://www.nexussafe.com) | Y      | N      | Basic/OAuth |                   |
| Janaka Ranabahu | [WSO2](http://wso2.com/products/identity-server/) | Y      | Y      | Basic | http://people.wso2.com:8080/charonDemoApp/interop_details.html |
| Brian Milas | [Courion](http://www.courion.com) | N      | Y      | Basic/OAuth2 | https://labs.courion.com/scim |
| Chuck Mortimore | [Salesforce](http://www.salesforce.com) | Y      | Y      | OAuth | https://scim-developer-edition.my.salesforce.com/services/apexrest/scim/v1/ ( https://login.salesforce.com/services/oauth2/authorize interop@simplecloud.info/test1234 client\_id=3MVG9QDx8IX8nP5Q3Qg39jXJDGh\_SESgJ6BqovTyXh\_UuSc5O0nUCqYS5nWwKF82nbYpejJXFr0H.nZGxV2Xl client\_secret=1981419349128675123 )   |
| Michael Schwartz | [Gluu](http://www.gluu.org/) | N      | Y      | Basic | http://ox.gluu.org/doku.php?id=scim:interop1 |
| Travis Spencer | [Ping](https://www.pingidentity.com/) | N      | Y      | Basic |                   |

# How #

## Demo Hour ##

TBD - Come up with details about how demo should look.  Likely will divide into client server pairs and show a subset of the use cases.

## Deep Dive ##

Attendees will be divided up into client and server pairs.  Each pair will try to execute as many use cases as possible, documenting successes and failures.  After a pair has completed their use cases, each attendee will be paired again with another.

To determine pairings and applicable use cases, each attendee must provide the following information.  If an attendee has both a client and a server, the supported options should be specified for each.  Note that most of this is described by the service provider configuration resource:

  * **Client**: Y/N
  * **Server**: Y/N
  * **Represenation**: JSON/XML/Both
  * **Authentication**: HTTP basic/OAuth
  * **Supported User Operations**
    * Create (POST)
    * Update (PUT)
    * Update (PATCH)
    * Retrieve (GET)
    * List (GET)
    * List with filter (GET)
    * List with sorting (GET)
    * Delete (DELETE)
    * Change Password (PUT or PATCH)
  * **Supported Group Operations**
    * Create (POST)
    * Update (PUT)
    * Update (PATCH)
    * Retrieve (GET)
    * List (GET)
    * List with filter (GET)
    * List with sorting (GET)
    * Delete (DELETE)
  * **Service Provider Config supported**: Y/N
  * **Schema resource supported**: Y/N
  * **Bulk supported**: Y/N
  * **ETag supported**: Y/N
  * **Other considerations**: For example, are there any required attributes for user creation.


If possible, attendees with server implementations should provide public access to their server prior to the interop event.  Please provide the following information either prior to or at the event:

  * **Server URL**:
  * **Authentication information**: username/password or OAuth bearer token information


# Use Cases #

Each pair should attempt the following use cases if supported by both the client and the server.

  1. Create user.
  1. Retrieve user created in previous use case.
  1. List users.  Ensure user from previous use case is present.
  1. List users with "attributes" query parameter.
  1. List users with filter.  Ensure user from use case 1 is/isn't present.
  1. List users with sorting.
  1. Update user using PUT.
  1. Update user using PATCH.
  1. Change user password.  Verify by authenticating with server natively if possible (eg - an LDAP bind).
  1. Create group.
  1. Retrieve group created in use previous use case.
  1. List groups.  Ensure group from previous use case is present.
  1. List groups with "attributes" query parameter.
  1. List groups with filter.  Ensure group from previous use case is/isn't present.
  1. List groups with sorting.
  1. Update group using PUT.
    * Modify simple displayName property
    * Add user
    * Remove user
  1. Update group using PATCH.
    * Modify simple displayName property
    * Add user
    * Remove user
  1. Delete user
  1. Submit bulk request to update two users.
  1. Retrieve provider config.
  1. Retrieve schemas.


# Results #

The results of the interop can be viewed and edited in the [interop results spreadsheet](https://docs.google.com/spreadsheet/ccc?key=0AtYxhHKU0YhodHpkcGFEUDVBY3ZJY1lqUUYwdWc2NUE).