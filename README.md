# Rail402 status

The public availability record of Rail402's hosted x402 services on Stellar: <https://status.rail402.dev>.

Checks run every 5 minutes from GitHub Actions, outside the services' host, with
[Upptime](https://github.com/upptime/upptime) (MIT). Every check is a read-only HTTPS GET with a content
assertion, listed in [`.upptimerc.yml`](.upptimerc.yml); no check pays, signs or writes anything.

| Check | What counts as up |
| --- | --- |
| `/supported` | HTTP 200 and the body advertises `"areFeesSponsored":true` (testnet) or `stellar:pubnet` (mainnet) |
| `/ready/testnet`, `/ready/pubnet` | HTTP 200 and `"ready":true`: each network's RPC, sponsor and channels |
| `/health` | HTTP 200 and the service is not starting |
| `/discovery/resources` | HTTP 200 with an `items` list |
| `/discovery/search` | HTTP 200 with `partialResults` |
| `/mcp/testnet`, `/mcp/pubnet` | the hosted MCP endpoint answers a GET with its own `method_not_allowed` error (it takes JSON-RPC over POST) |
| Explorer, Playground, demo seller, documentation | HTTP 200 (the demo seller: 402) |

**Availability** is Upptime's figure: a failed check opens an issue here, the next passing check closes it,
and a check's uptime is the share of the window not covered by those issues. Checks run about every 5
minutes (GitHub can delay or skip scheduled runs), so an outage that starts and ends between two runs is not
seen, and an outage's length is known only to the check interval. The history is this repository's git log,
`history/` and its issues.

The page at status.rail402.dev reads `history/summary.json` from this repository. The incidents it shows are
written by the operators after review; the issues opened here by the checks are the raw record.

Something not working? Open an issue on [tolgayayci/rail402](https://github.com/tolgayayci/rail402/issues/new)
or write to tolga@yk-labs.com.

Checks run about every five minutes, so an interruption shorter than that can pass between two checks. Availability here means the checks passed.
