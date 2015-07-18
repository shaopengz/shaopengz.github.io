title: "fix protocol knowledge"
date: 2015-06-15 18:05:26
tags:
- finance
- network
- protocol
---

Body Length = 65bt

### Classification of Protocol:
1. Admin Message ( Session Message)
2. Application Message( Trade, Pre-Trade, Post-Trade Message)


### MsgType = D: newOrderSingle - place a order
               = G: OrderCancelReplance - change quality and price
               = F: cancel order placed into market
               = 0: HeartBeat
               = 1: requestHeartBeat
               = 2: resend
               = 3: Session Level reject
               = 4: fill gap/seq reset
               = j: business level reject

### common issue:
network connectivity
firewall
incorrect host/port number
SenderCompID/TargetCompID
seq num mismatch
different FIX version

### two reason be logged out
1. your seq is less than broker expects, u need to outgoing reset seq;
2. your engine can logout broker if your expected seq is larger than broker incoming seq, our need to reset your incoming seq num.

first check logon message( MsgType = A or 35=A) to verify connection between client and broker Engine.
check logout message( MsgType = 5 or 35=5)

### Common Tag Num
Tag 9 = body length
Tag 10 = Check Sum
Tag 34 = Seq No.
Tag 44 = price
Tag 49 = SenderCompID
Tag 56 = TargetCompID
Tag 58 = reject reason
Tag 97 = PossResend
Tag 112 = TestRequestID
Tag 123 = GapFillFlag

### Seq Reset Mode
Gap Fill( tag 123 is ‘Y’)
Recover Mode(tag 123 is ’N’)

#### PartyID repeating group tags
453 NoPartyIDs(No should be Num)
448 PartyID
447 PartyIDSource
452 PartyRole

### repeating group summary
-- When group of tags appear multiple times in a FIX message we call them repeating group.
   -- Number tag is a leading tag which specifies how many repeating groups are present in the FIX message e.g. NoPartyIDs
   -- First tag specified in FIX Message specification is used as marker tag to mark start and end of a FIX message.
   -- No of repeating groups must match with the number specified by No### tag e.g. NoPartyIDs
   -- Follow the order of tags specified in the FIX Message specification while constructing a repeating group
   -- A Repeating group can contain another repeating group within it.
   -- PartyID blocks are introduced in FIX 4.3 so it will not work on earlier FIX protocol versions. 

### Message Reject
- MsgType = 8 Exectuion Report, 
- MsgType = 9, cancelOrderReject (order have been full-filled in the market)
1) Account not mapped correctly on broker side.
2) Unknown ID
3) Valid but unsupported message type
4) Unknown security
5) Valid but unknown message type.
6) Some of conditionally required field is not present in Incoming FIX message.