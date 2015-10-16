# Goal #
The usual.  Bang up as many implementations as we can.  Primarily this should find weaknesses in the implementations and - more importantly - the spec.


# When & Where #

IETF 83 Paris - [Hotel Concorde La Fayette](http://www.concorde-lafayette.com/en/paris-events/mezzanine.aspx) - Room Corot

Wednesday March 28, 2012 - 12:00-18:00 CET (tentatively)

Remote participation will be available for attendees that cannot attend IETF.  Logistics still need to be worked out, but this will probably work best for attendees that have public SCIM servers.  Remote participation may be difficult for SCIM clients if servers are not public.

# Who #

| Person | Representing | Client | Server | Auth | Download/Endpoint |
|:-------|:-------------|:-------|:-------|:-----|:------------------|
| Trey Drake | [UnboundID](http://www.unboundid.com) | Y      | Y      | Server Basic only, Client Basic and OAuth | http://code.google.com/p/scimsdk/ |
| Kelly Grizzle | [SailPoint](http://www.sailpoint.com) | Y      | N      | Basic/OAuth |
| Erik Wahlström & Samuel Erdtman | [Technology Nexus](http://www.nexussafe.com) | Y      | Y      | Basic/OAuth |https://groups.google.com/group/cloud-directory/browse_thread/thread/ee92191169d1c571|
| Emmanuel Dreux | [BCPSOFT](http://www.bcpsoft.fr) | Y      | Y      | Basic/OAuth(client) |
| Hasini Gunasinghe | [WSO2](http://wso2.org/library/identity-server) | Y      | Y      | Basic/OAuth | http://people.wso2.com:8080/charonDemoApp/interop_details.html |
| Travis Spencer | [Ping](https://www.pingidentity.com/) | N      | Y      | Basic |
| Michael Schwartz (remote) | [Gluu](http://www.gluu.org/) | N      | Y      | ?    | http://ox.gluu.org/doku.php?id=scim:interop1 |
| Brian Milas (remote) | [Courion](http://www.courion.com/) | N      | Y      | OAuth |  https://labs.courion.com/scim/ |
| Chuck Mortimore | [Salesforce.com](http://www.salesforce.com/) | Y      | Y      | OAuth | https://scim-developer-edition.my.salesforce.com/services/apexrest/scim/v1/   ( https://login.salesforce.com/services/oauth2/authorize interop@simplecloud.info/test1234  client\_id=3MVG9QDx8IX8nP5Q3Qg39jXJDGh\_SESgJ6BqovTyXh\_UuSc5O0nUCqYS5nWwKF82nbYpejJXFr0H.nZGxV2Xl client\_secret=1981419349128675123 )|

# How #

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
    * Add user
    * Remove user
  1. Update group using PATCH.
    * Add user
    * Remove user
  1. Delete user
  1. Submit bulk request to update two users.
  1. Retrieve provider config.
  1. Retrieve schemas.


# Results #

The results of the interop can be viewed and edited in the [interop results spreadsheet](https://docs.google.com/spreadsheet/ccc?key=0AtYxhHKU0YhodEdEaW1TaUsyM2h2cjhjbllabkhuUWc).