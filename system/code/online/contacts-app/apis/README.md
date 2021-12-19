# 👥 Contacts service

The is the multi-tenant back-end service for contacts app.

This section is incomplete ...

## 🎬 Scenarios

* Contacts app creates a new account on behalf of consumer
* Contacts app updates contacts on behalf of consumer
* Contacts app adds, updates or deletes contact information on behalf of consumer
* Contacts app sets up a new beacon public URI on behalf of consumer

## 🎰 Functionality

* Account creation and access
* Contacts access (create, update, delete)
* Beacon activation on unique URI
* Connection access (create, update, delete)
* // Contact sharing

## 🗜 Interfaces

Service APIs for discovery and high level account operations:

```
public class DiscoveryService
{
}
```

Service APIs for IdBox, identity and connection access

```
public class IdBoxService
{
}
```

Service APIs for Beacon URI activation:

```
public class PublicUriService
{
}
```
