---
Description: This section describes messages and message queues and how to use them in your applications.
ms.assetid: 21a4d40b-52da-49e4-a374-afc4927e96e8
title: Messages and Message Queues
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Messages and Message Queues

This section describes messages and message queues and how to use them in your applications.

### In This Section



| Name                                                                       | Description                                                                                                                                |
|----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| [About Messages and Message Queues](about-messages-and-message-queues.md) | This section discusses Windows messages and message queues.<br/>                                                                     |
| [Using Messages and Message Queues](using-messages-and-message-queues.md) | The following code examples demonstrate how to perform the following tasks associated with Windows messages and message queues.<br/> |
| [Message Reference](message-and-message-queue-reference.md)               | Contains the API reference.<br/>                                                                                                     |



 

### System-Provided Messages

For lists of the system-provided messages, see [System-Defined Messages](about-messages-and-message-queues.md#system-defined-messages).

### Message Functions



| Name                                                         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**BroadcastSystemMessage**](broadcastsystemmessage.md)     | Sends a message to the specified recipients. The recipients can be applications, installable drivers, network drivers, system-level device drivers, or any combination of these system components. <br/> To receive additional information if the request is defined, use the [**BroadcastSystemMessageEx**](broadcastsystemmessageex.md) function.<br/>                                                                                                                                                                                                                                  |
| [**BroadcastSystemMessageEx**](broadcastsystemmessageex.md) | Sends a message to the specified recipients. The recipients can be applications, installable drivers, network drivers, system-level device drivers, or any combination of these system components. <br/> This function is similar to [**BroadcastSystemMessage**](broadcastsystemmessage.md) except that this function can return more information from the recipients.<br/>                                                                                                                                                                                                              |
| [**DispatchMessage**](dispatchmessage.md)                   | Dispatches a message to a window procedure. It is typically used to dispatch a message retrieved by the [**GetMessage**](/windows/win32/Winuser/nf-engextcpp-extexception-getmessage?branch=master) function.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| [**GetInputState**](getinputstate.md)                       | Determines whether there are mouse-button or keyboard messages in the calling thread's message queue. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| [**GetMessage**](/windows/win32/Winuser/nf-engextcpp-extexception-getmessage?branch=master)                             | Retrieves a message from the calling thread's message queue. The function dispatches incoming sent messages until a posted message is available for retrieval. <br/> Unlike [**GetMessage**](/windows/win32/Winuser/nf-engextcpp-extexception-getmessage?branch=master), the [**PeekMessage**](peekmessage.md) function does not wait for a message to be posted before returning.<br/>                                                                                                                                                                                                                                                              |
| [**GetMessageExtraInfo**](getmessageextrainfo.md)           | Retrieves the extra message information for the current thread. Extra message information is an application- or driver-defined value associated with the current thread's message queue. <br/>                                                                                                                                                                                                                                                                                                                                                                                                   |
| [**GetMessagePos**](getmessagepos.md)                       | Retrieves the cursor position for the last message retrieved by the [**GetMessage**](/windows/win32/Winuser/nf-engextcpp-extexception-getmessage?branch=master) function. <br/> To determine the current position of the cursor, use the [**GetCursorPos**](https://msdn.microsoft.com/library/windows/desktop/ms648390) function.<br/>                                                                                                                                                                                                                                                                                                                                                       |
| [**GetMessageTime**](getmessagetime.md)                     | Retrieves the message time for the last message retrieved by the [**GetMessage**](/windows/win32/Winuser/nf-engextcpp-extexception-getmessage?branch=master) function. The time is a long integer that specifies the elapsed time, in milliseconds, from the time the system was started to the time the message was created (that is, placed in the thread's message queue). <br/>                                                                                                                                                                                                                                                                         |
| [**GetQueueStatus**](getqueuestatus.md)                     | Indicates the type of messages found in the calling thread's message queue.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| [**InSendMessage**](insendmessage.md)                       | Determines whether the current window procedure is processing a message that was sent from another thread (in the same process or a different process) by a call to the [**SendMessage**](sendmessage.md) function. <br/> To obtain additional information about how the message was sent, use the [**InSendMessageEx**](insendmessageex.md) function.<br/>                                                                                                                                                                                                                              |
| [**InSendMessageEx**](insendmessageex.md)                   | Determines whether the current window procedure is processing a message that was sent from another thread (in the same process or a different process).<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| [**PeekMessage**](peekmessage.md)                           | Dispatches incoming sent messages, checks the thread message queue for a posted message, and retrieves the message (if any exist).<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| [**PostMessage**](postmessage.md)                           | Posts a message in the message queue associated with the thread that created the specified window and returns without waiting for the thread to process the message. <br/> To post a message in the message queue associated with a thread, use the [**PostThreadMessage**](postthreadmessage.md) function.<br/>                                                                                                                                                                                                                                                                          |
| [**PostQuitMessage**](postquitmessage.md)                   | Indicates to the system that a thread has made a request to terminate (quit). It is typically used in response to a [**WM\_DESTROY**](wm-destroy.md) message.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [**PostThreadMessage**](postthreadmessage.md)               | Posts a message to the message queue of the specified thread. It returns without waiting for the thread to process the message.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**RegisterWindowMessage**](registerwindowmessage.md)       | Defines a new window message that is guaranteed to be unique throughout the system. The message value can be used when sending or posting messages.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| [**ReplyMessage**](replymessage.md)                         | Replies to a message sent through the [**SendMessage**](sendmessage.md) function without returning control to the function that called **SendMessage**.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [*SendAsyncProc*](sendasyncproc.md)                         | An application-defined callback function used with the [**SendMessageCallback**](sendmessagecallback.md) function. The system passes the message to the callback function after passing the message to the destination window procedure. The **SENDASYNCPROC** type defines a pointer to this callback function. [*SendAsyncProc*](sendasyncproc.md) is a placeholder for the application-defined function name.<br/>                                                                                                                                                                          |
| [**SendMessage**](sendmessage.md)                           | Sends the specified message to a window or windows. The [**SendMessage**](sendmessage.md) function calls the window procedure for the specified window and does not return until the window procedure has processed the message. <br/> To send a message and return immediately, use the [**SendMessageCallback**](sendmessagecallback.md) or [**SendNotifyMessage**](sendnotifymessage.md) function. To post a message to a thread's message queue and return immediately, use the [**PostMessage**](postmessage.md) or [**PostThreadMessage**](postthreadmessage.md) function.<br/> |
| [**SendMessageCallback**](sendmessagecallback.md)           | Sends the specified message to a window or windows. It calls the window procedure for the specified window and returns immediately. After the window procedure processes the message, the system calls the specified callback function, passing the result of the message processing and an application-defined value to the callback function.<br/>                                                                                                                                                                                                                                             |
| [**SendMessageTimeout**](sendmessagetimeout.md)             | Sends the specified message to one of more windows.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| [**SendNotifyMessage**](sendnotifymessage.md)               | Sends the specified message to a window or windows. If the window was created by the calling thread, [**SendNotifyMessage**](sendnotifymessage.md) calls the window procedure for the window and does not return until the window procedure has processed the message. If the window was created by a different thread, **SendNotifyMessage** passes the message to the window procedure and returns immediately; it does not wait for the window procedure to finish processing the message.<br/>                                                                                              |
| [**SetMessageExtraInfo**](setmessageextrainfo.md)           | Sets the extra message information for the current thread. Extra message information is an application- or driver-defined value associated with the current thread's message queue. An application can use the [**GetMessageExtraInfo**](getmessageextrainfo.md) function to retrieve a thread's extra message information.<br/>                                                                                                                                                                                                                                                                |
| [**TranslateMessage**](translatemessage.md)                 | Translates virtual-key messages into character messages. The character messages are posted to the calling thread's message queue, to be read the next time the thread calls the [**GetMessage**](/windows/win32/Winuser/nf-engextcpp-extexception-getmessage?branch=master) or [**PeekMessage**](peekmessage.md) function.<br/>                                                                                                                                                                                                                                                                                                                            |
| [**WaitMessage**](waitmessage.md)                           | Yields control to other threads when a thread has no other messages in its message queue. The [**WaitMessage**](waitmessage.md) function suspends the thread and does not return until a new message is placed in the thread's message queue.<br/>                                                                                                                                                                                                                                                                                                                                              |



 

### Message Constants



| Name                             | Description                                                                    |
|----------------------------------|--------------------------------------------------------------------------------|
| [**OCM\_\_BASE**](ocm--base.md) | Used to define private messages for use by private window classes. <br/> |
| [**WM\_APP**](wm-app.md)        | Used to define private messages. <br/>                                   |
| [**WM\_USER**](wm-user.md)      | Used todefine private messages for use by private window classes. <br/>  |



 

### Message Structures



| Name                       | Description                                                                                                                              |
|----------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| [**BSMINFO**](bsminfo.md) | Contains information about a window that denied a request from [**BroadcastSystemMessageEx**](broadcastsystemmessageex.md). <br/> |
| [**MSG**](/windows/win32/Winuser/nf-engextcpp-ext_status_emsg?branch=master)         | Contains message information from a thread's message queue. <br/>                                                                  |



 

 

 



