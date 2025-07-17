# Rate Limiter Module

## General Description and Objectives
The Rate Limiter module provides IBC packet rate limiting for KiiChain. It helps prevent spam, abuse, and excessive resource consumption by enforcing configurable limits on IBC transfers and other cross-chain operations.

**Objectives:**
- Protect the network from spam and abuse via IBC
- Enforce configurable rate limits on IBC packets and transfers
- Provide monitoring and analytics for rate-limited actions

## Main Function Calls
- Set and update rate limit parameters for IBC channels and tokens
- Enforce rate limits on incoming and outgoing IBC packets
- Monitor and log rate-limited events

## Queries
- Query current rate limits and usage statistics
- Retrieve configuration and status for specific IBC channels or tokens

## Usage Examples

### Querying Rate Limits (CLI)
You can query the current rate limits for a channel using the CLI:

```sh
kiid q ratelimiter rate-limits --channel-id <channel-id>
```

### Updating Rate Limit Parameters (CLI)
To update rate limit parameters for a channel:

```sh
kiid tx ratelimiter update-rate-limit --channel-id <channel-id> --max-tokens 1000000 --window 3600 --from <your-key>
```

### Querying Usage Statistics (CLI)
```sh
kiid q ratelimiter usage --channel-id <channel-id>
```

## Reference
- [cosmos/ibc-apps rate-limiting module](https://github.com/cosmos/ibc-apps/tree/main/modules/rate-limiting)
