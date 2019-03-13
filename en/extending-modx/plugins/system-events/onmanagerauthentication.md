---
title: "OnManagerAuthentication"
_old_id: "431"
_old_uri: "2.x/developing-in-modx/basic-development/plugins/system-events/onmanagerauthentication"
---

## Event: OnManagerAuthentication

Fires right before the user is authenticated or its session is added to the manager context. This event can be used to provide external authentication support. This event is used to ALLOW login.

If its output is true, or an array where at least one index is set to true, then MODx will assume that the user has successfully logged in and bypass the default authentication via password.

Service: 2 - Manager Access Events 
Group: None

## Event Parameters

| Name               | Description                                                                         |
| ------------------ | ----------------------------------------------------------------------------------- |
| **&** user         | A reference to the modUser object. **Passed by reference**                          |
| password           | The provided password.                                                              |
| rememberme         | Whether or not to remember the user via cookie.                                     |
| lifetime           | The lifetime of the session cookie.                                                 |
| **&** loginContext | The context key this login is occurring in. **Passed by reference**                 |
| **&** addContexts  | Additional contexts in which the login is also occuring in. **Passed by reference** |

## Event Login Workflow

1. _[_OnBeforeWebLogin_](http://rtfm.modx.com/display/revolution20/OnBeforeWebLogin)_ || _[OnBeforeManagerLogin](http://rtfm.modx.com/display/revolution20/OnBeforeManagerLogin)_ - Inside this event the developer can check for erroneous parameters which will **disallow** further logging in process. If plugins executed by this event return something except true, the logging in will be aborted with the specified error.
2. _[OnUserNotFound](http://rtfm.modx.com/display/revolution20/OnUserNotFound)_ - This event is executed only if the provided username is not found inside MODX database. The developer can provide it's own modUser object in the event output to continue the login process.
3. _[OnWebAuthentication](http://rtfm.modx.com/display/revolution20/OnWebAuthentication)_ || **_OnManagerAuthentication_** - Inside this event the developer can check for parameters which will **override the default checking by password** and **allow** further logging in process. If one of the plugins executed from this event return true, the user is considered verified and logged in.
4. _[OnWebLogin](http://rtfm.modx.com/display/revolution20/OnWebLogin)_ || _[OnManagerLogin](http://rtfm.modx.com/display/revolution20/OnManagerLogin)_ - This event is fired after the logging in process has finished and the user is considered logged in. It **doesn't change** the logging in process **behaviour**.

## See Also

- [System Events](developing-in-modx/basic-development/plugins/system-events "System Events")
- [Plugins](developing-in-modx/basic-development/plugins "Plugins")