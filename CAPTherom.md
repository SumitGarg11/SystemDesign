#  CAP theorem
```
The CAP theorem, introduced by Eric Brewer in 2000, provides a fundamental framework for understanding the trade-offs that must be made when designing distributed systems.
```
### CAP stands for Consistency, Availability, and Partition Tolerance, and the theorem states that:

```
It is impossible for a distributed data store to simultaneously provide all three guarantees.
```

## What does Consistency (C) mean?

- Every read receives the most recent write or an error.
  
```
Imagine you are using Google Docs to edit a document with a friend.

You type a new sentence and save it.
Your friend opens the document.
If Consistency (C) is guaranteed, they will see your latest changes immediately or they will get an error (like "document not available right now") instead of old or missing data.
In short:

No outdated or incorrect data.
Either see the latest update or get an error (wait until data is correct).

```

```

Real-world example in databases:
In a banking system, when you transfer ₹1000 from Account A to Account B:
If you check the balance right after the transfer, it must be correct (not an old value).
If the system is not ready to show the correct balance, it will give an error instead of wrong data.

```

## Availability (A): 
- Every request (read or write) receives a non-error response, without guarantee that it contains the most recent write.

- Every request (read or write) gets a response, but it might not be the latest data.

- Availability (A) means the system always responds (it won’t show an error).

```
Example: Twitter Likes & Retweets Count
Imagine you are using Twitter (X) and you like a tweet.

How does Availability work here?
You tap the like button on a tweet.
The like count immediately increases on your screen (let’s say from 100 to 101).
But due to a delay in syncing across all servers, another user checking the same tweet might still see 100 likes for a few seconds before it updates.
The system never shows an error—it always returns some data (even if it’s slightly outdated).

```

# What does Partition Tolerance (P) mean?

- The system keeps running even if some network connections fail or messages between servers are lost/delayed.

```
 Example: WhatsApp Messages
You send a message to a friend.
Your internet suddenly disconnects.
WhatsApp does not lose your message—it shows a single gray tick (indicating the message is waiting to be sent).
As soon as the internet is restored, the message gets delivered.
💡 Why WhatsApp prioritizes Partition Tolerance?

Even if the network fails, messages are not lost—they are sent when possible.

```
- Key Takeaway
✔ Partition Tolerance (P) means the system keeps running even if network issues occur.
❌ But there may be delays in syncing data across different servers.