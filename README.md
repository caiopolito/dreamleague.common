# dreamleague.common

Shared .NET class library containing all domain entities and DTOs used across the [DreamLeague](https://github.com/caiopolito/dreamleague) platform.

## What is DreamLeague?

DreamLeague is a third-party matchmaking platform for CS2. Players authenticate via Steam, queue for matches, get assigned to a dedicated CS2 game server, and stats are recorded automatically via the MatchZy plugin. If you landed here first, the main repository with the full platform (API, frontend, game server, and databases) is at **[github.com/caiopolito/dreamleague](https://github.com/caiopolito/dreamleague)**.

## What's in this package

| Namespace | Contents |
|---|---|
| `Entities.Players` | `Player`, `PlayerFilter` |
| `Entities.Teams` | `Team`, `PlayerTeam` |
| `Entities.Matches` | `OngoingMatch` |
| `Entities.Get5` | `Match`, `TeamMatch`, `MapStats`, `PlayerStats`, `PlayerResults`, `MatchResult` |
| `Entities.Rcon` | `RconMatch`, `RconAvailable` |
| `Entities.Servers` | `Server`, `ServerConnection` |
| `Entities.Chat` | `ChatInfo`, `Message` |
| `Entities.Notifications` | `TeamNotification` |
| `Entities.Championships` | `Championship` |
| `Entities.Steam` | Steam Web API response types (`SteamPlayer`, `PlayerFriends`, etc.) |
| `Entities.HealthCheck` | `HealthCheckActivity`, `HealthCheckStatus` |
| `Enums.Ranks` | `RanksEnum` |

> The `Get5` namespace uses legacy naming retained for compatibility — DreamLeague uses a custom MatchZy fork, not the GET5 plugin directly.

## Installation

The package is published to GitHub Packages. Add the feed to your `nuget.config`:

```xml
<packageSources>
  <add key="github" value="https://nuget.pkg.github.com/caiopolito/index.json" />
</packageSources>
<packageSourceCredentials>
  <github>
    <add key="Username" value="caiopolito" />
    <add key="ClearTextPassword" value="%GITHUB_TOKEN%" />
  </github>
</packageSourceCredentials>
```

Then install the package:

```bash
dotnet add package dreamleague.common
```

Authentication requires a GitHub personal access token with `read:packages` scope set as `GITHUB_TOKEN` in your environment.

## License

MIT — see [LICENSE.txt](LICENSE.txt).
