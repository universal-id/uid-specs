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

Minimal API for the Apps controller is as follows:

```
public class AppsController
{
    public void RegisterApp(string uniqueId);
    public void NotifyAppEvent(AppEvent appEvent)
}

public class AppEvent
{
}

public class AppStarted : AppEvent
{
    public DateTime StartedDateTime { get; set; }
}
```

Example for the the data stored in the database for apps is as follows:

```
{
    "uniqueId" : "123ABC434B...DEF234798",
    "lastLoggedIn" : "12346573" // Linux date time format
}    
```
