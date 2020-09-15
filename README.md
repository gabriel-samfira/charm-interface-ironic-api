# Overview

This interface provides information about the Ironic API readiness to charms that consume it. The purpose of this interface, is to notify charms when the Ironic API is fully functional, so as consumers can write apropriate configs and restart any needed services.

# Requires

No explicit handler is required to consume this interface in charms that consume this interface.

This interface sets ```{relation_name}.available``` when the remote Ironic API charm has finished configuring the API service.

# Provides

The interface layer will set the following states, as appropriate:

  * {relation_name}.connected The relation is established, but the client has not provided the database information yet.
  * {relation_name}.available The requested information is complete. The DB, user and hostname can be created.
  * connection information is passed back to the client with the following method:
    * set_baremetal_info()
