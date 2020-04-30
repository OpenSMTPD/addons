# Filters

This directory contains a list of **third-party contributed** filters to be used with OpenSMTPD.


## filter-greylist
This filter implements greylisting, allowing OpenSMTPD to temporarily reject sessions of clients it has not seen before. Unlike many implementations, this one is SPF-aware so it will properly handle greylisting for domains doing relaying through multiple MX, as long as they publish a valid SPF record.

This initial version is a proof of concept, it does not persist state outside of memory, and might suffer from bugs.

Do not use in production (yet).

## filter-rspamd
This filter implements the Rspamd protocol and allows OpenSMTPD to request an Rspamd analysis of an SMTP transaction before a message is committed to queue.

## filter-senderscore
This filter performs a SenderScore lookup and allows OpenSMTPD to either block or slow down a session based on the reputation of the source IP address.