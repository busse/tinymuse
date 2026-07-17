# TinyMUSE Command Reference

This reference documents every built-in command recognized by the in-game command parser in TinyMUSE.

## Scope and sources

- Primary parser: `process_command()` in `src/game.c`
- Single-character command tokens: `src/config.h`
- Matching rule: `Matched(...)` uses `string_prefix(...)`, so command abbreviations are accepted when unambiguous (`src/game.c:28`, `src/stringutil.c:36`).

## Single-character command tokens

| Token | Expands to | Source |
|---|---|---|
| `"` | `say` | `src/config.h:38`, `src/game.c:813` |
| `:` | `pose` (space-preserving) | `src/config.h:39`, `src/game.c:817` |
| `;` | `pose` (no inserted space) | `src/config.h:40`, `src/game.c:821` |
| `=` | `+com` on your default channel | `src/config.h:41`, `src/game.c:825` |
| `'` | `to` | `src/config.h:42`, `src/game.c:829` |

## Built-in player commands (no prefix)

| Command | Handler | Source |
|---|---|---|
| `drop` | `do_drop` | `src/game.c:1917` |
| `enter` | `do_enter` | `src/game.c:1931` |
| `examine` | `do_examine` | `src/game.c:1926` |
| `follow` | `do_follow` | `src/game.c:1940` |
| `get` | `do_get` | `src/game.c:1950` |
| `give` | `do_give` | `src/game.c:1955` |
| `goto` | `do_move` | `src/game.c:1960` |
| `gripe` | `do_gripe` | `src/game.c:1965` |
| `help` | `do_text` | `src/game.c:1974` |
| `home` | `do_move` | `src/game.c:790` |
| `inventory` | `do_inventory` | `src/game.c:1980` |
| `join` | `do_join` | `src/game.c:1985` |
| `leave` | `do_leave` | `src/game.c:1999` |
| `look` | `do_look_at` | `src/game.c:877` |
| `money` | `do_money` | `src/game.c:2016` |
| `move` | `do_move` | `src/game.c:2021` |
| `news` | `do_text` | `src/game.c:2035` |
| `page` | `do_page` | `src/game.c:2048` |
| `pose` | `do_pose` | `src/game.c:2053` |
| `read` | `do_look_at` | `src/game.c:2066` |
| `say` | `do_say` | `src/game.c:2080` |
| `score` | `do_score` | `src/game.c:2092` |
| `slay` | `do_slay` | `src/game.c:2097` |
| `summon` | `do_summon` | `src/game.c:2102` |
| `take` | `do_get` | `src/game.c:2115` |
| `throw` | `do_drop` | `src/game.c:2120` |
| `to` | `do_to` | `src/game.c:2125` |
| `use` | `do_use` | `src/game.c:2134` |
| `whisper` | `do_whisper` | `src/game.c:2148` |
| `who` | `dump_users` | `src/game.c:2160` |

## Built-in `+` commands

| Command | Handler | Source |
|---|---|---|
| `+away` | `do_away` | `src/game.c:891` |
| `+channel` | `do_channel` | `src/game.c:918` |
| `+cmdav` | `do_cmdav` | `src/game.c:913` |
| `+com` | `do_com` | `src/game.c:901` |
| `+ctitle` | `do_ctitle` | `src/game.c:930` |
| `+haven` | `do_haven` | `src/game.c:939` |
| `+idle` | `do_idle` | `src/game.c:944` |
| `+laston` | `do_laston` | `src/game.c:952` |
| `+mail` | `do_mail` | `src/game.c:963` |
| `+uptime` | `do_uptime` | `src/game.c:971` |
| `+version` | `do_version` | `src/game.c:976` |

## Built-in `@` commands

| Command | Handler | Source |
|---|---|---|
| `@addparent` | `do_addparent` | `src/game.c:991` |
| `@allquota` | `do_allquota` | `src/game.c:1003` |
| `@announce` | `do_announce` | `src/game.c:1009` |
| `@as` | `do_as` | `src/game.c:1020` |
| `@at` | `do_at` | `src/game.c:1014` |
| `@boot` | `do_boot` | `src/game.c:1039` |
| `@broadcast` | `do_broadcast` | `src/game.c:1034` |
| `@cboot` | `do_cboot` | `src/game.c:1053` |
| `@cemit` | `do_cemit` | `src/game.c:1058` |
| `@check` | `do_check` | `src/game.c:1085` |
| `@chown` | `do_chown` | `src/game.c:1073` |
| `@chownall` | `do_chownall` | `src/game.c:1063` |
| `@class` | `do_class` | `src/game.c:1115` |
| `@clearmail` | `clear_old_mail` | `src/game.c:1124` |
| `@clone` | `do_clone` | `src/game.c:1130` |
| `@config` | `do_config` | `src/game.c:1140` |
| `@cpage` | `do_cpage` | `src/game.c:1095` |
| `@create` | `do_create` | `src/game.c:1100` |
| `@cset` | `do_set` | `src/game.c:1145` |
| `@ctrace` | `do_ctrace` | `src/game.c:1106` |
| `@cycle` | `do_cycle` | `src/game.c:1151` |
| `@dbck` | `do_dbck` | `src/game.c:1170` |
| `@dbtop` | `do_dbtop` | `src/game.c:1175` |
| `@decompile` | `do_decompile` | `src/game.c:1188` |
| `@defattr` | `do_defattr` | `src/game.c:1213` |
| `@delparent` | `do_delparent` | `src/game.c:1219` |
| `@describe` | `do_describe` | `src/game.c:1198` |
| `@destroy` | `do_recycle` | `src/game.c:1203` |
| `@dig` | `do_dig` | `src/game.c:1229` |
| `@dump` | `do_dump` | `src/game.c:1235` |
| `@echo` | `do_echo` | `src/game.c:1277` |
| `@edit` | `do_edit` | `src/game.c:1289` |
| `@emit` | `do_emit` | `src/game.c:1299` |
| `@empower` | `do_empower` | `src/game.c:1311` |
| `@find` | `do_find` | `src/game.c:1248` |
| `@force` | `do_force` | `src/game.c:1263` |
| `@foreach` | `do_foreach` | `src/game.c:1256` |
| `@gethost` | `do_gethost` | `src/game.c:1339` |
| `@giveto` | `do_giveto` | `src/game.c:1334` |
| `@halt` | `do_halt` | `src/game.c:1353` |
| `@hide` | `do_hide` | `src/game.c:1358` |
| `@info` | `do_info` | `src/game.c:1367` |
| `@link` | `do_link` | `src/game.c:1377` |
| `@lockout` | `do_lockout` | `src/game.c:1387` |
| `@misc` | `do_misc` | `src/game.c:1400` |
| `@name` | `do_name` | `src/game.c:1409` |
| `@ncset` | `do_set` | `src/game.c:1414` |
| `@necho` | `do_echo` | `src/game.c:1423` |
| `@nemit` | `do_emit` | `src/game.c:1433` |
| `@newpassword` | `do_newpassword` | `src/game.c:1427` |
| `@nologins` | `do_nologins` | `src/game.c:1445` |
| `@noop` | `do_nopow_class` | `src/game.c:1451` |
| `@nopow_class` | `do_nopow_class` | `src/game.c:1455` |
| `@npage` | `do_page` | `src/game.c:1473` |
| `@npemit` | `do_general_emit` | `src/game.c:1468` |
| `@nset` | `do_set` | `src/game.c:1482` |
| `@nuke` | `do_nuke` | `src/game.c:1488` |
| `@oemit` | `do_general_emit` | `src/game.c:1505` |
| `@open` | `do_open` | `src/game.c:1518` |
| `@outgoing` | `do_outgoing` | `src/game.c:1524` |
| `@password` | `do_password` | `src/game.c:1538` |
| `@pbreak` | `do_pstats` | `src/game.c:1543` |
| `@pcreate` | `do_pcreate` | `src/game.c:1548` |
| `@pemit` | `do_general_emit` | `src/game.c:1553` |
| `@Poor` | `do_poor` | `src/game.c:1569` |
| `@powers` | `do_powers` | `src/game.c:1578` |
| `@ps` | `do_queue` | `src/game.c:1587` |
| `@purge` | `do_purge` | `src/game.c:1592` |
| `@quota` | `do_quota` | `src/game.c:1601` |
| `@reboot` | `do_reboot` | `src/game.c:1614` |
| `@remit` | `do_general_emit` | `src/game.c:1619` |
| `@robot` | `do_robot` | `src/game.c:1635` |
| `@search` | `do_search` | `src/game.c:1652` |
| `@set` | `do_set` | `src/game.c:1658` |
| `@showhash` | `do_showhash` | `src/game.c:1676` |
| `@shutdown` | `do_shutdown` | `src/game.c:1671` |
| `@stats` | `do_stats` | `src/game.c:1685` |
| `@su` | `do_su` | `src/game.c:1690` |
| `@swap` | `do_swap` | `src/game.c:1700` |
| `@sweep` | `do_sweep` | `src/game.c:1705` |
| `@switch` | `do_switch` | `src/game.c:1710` |
| `@teleport` | `do_teleport` | `src/game.c:1732` |
| `@text` | `do_text` | `src/game.c:1738` |
| `@tr_as` | `do_trigger_as` | `src/game.c:1756` |
| `@trigger` | `do_trigger` | `src/game.c:1751` |
| `@ulink` | `do_ulink` | `src/game.c:1773` |
| `@undestroy` | `do_undestroy` | `src/game.c:1790` |
| `@unhide` | `do_unhide` | `src/game.c:1830` |
| `@unlink` | `do_unlink` | `src/game.c:1814` |
| `@unlock` | `do_unlock` | `src/game.c:1820` |
| `@unzlink` | `do_unzlink` | `src/game.c:1835` |
| `@upfront` | `do_upfront` | `src/game.c:1843` |
| `@usercap` | `do_usercap` | `src/game.c:1848` |
| `@wait` | `wait_que` | `src/game.c:1881` |
| `@wemit` | `do_wemit` | `src/game.c:1875` |
| `@whereis` | `do_whereis` | `src/game.c:1861` |
| `@wipeout` | `do_wipeout` | `src/game.c:1866` |
| `@zemit` | `do_general_emit` | `src/game.c:1891` |
| `@zlink` | `do_zlink` | `src/game.c:1903` |

## Notes and aliases

- `read` is an undocumented alias for `look` (`src/game.c:2066`).
- `take` aliases `get`, and `throw` aliases `drop` (`src/game.c:2115`, `src/game.c:2120`).
- `goto` and `move` both route to movement handling (`src/game.c:1960`, `src/game.c:2021`).
- `l` is accepted as `look` (`src/game.c:1993-1995`).
- `w` with no suffix routes to whisper behavior (`src/game.c:2167-2169`).
- If the command word matches one of your channel aliases, it is treated as a channel command (`src/game.c:2179-2185`).

## Command totals

- No-prefix commands: 30
- `+` commands: 11
- `@` commands: 99
- Total built-in parser-recognized commands: 140
