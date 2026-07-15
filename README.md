
> **📌 This repository hosts code for Exegol Sentinel, a component of the Exegol project.
> If you were looking for Exegol, go to [the main repo](https://github.com/ThePorgs/Exegol)**
___

# Exegol Sentinel official library

Exegol Sentinel runs alongside Exegol containers: it logs command activity in a structured (JSON) manner, and facilitates pulling from SIEM collecting agents.
Sentinel logs the commands as well as metadata including. Users can also defined triggers, actions and profiles to collect additional artifacts or run side effects (ticket dumps, packet captures, and so on).

Official catalog for Exegol Sentinel (YAML triggers, actions, profiles). For the time being, this library is a demo and includes minimal examples. In the future, it will grow along the users' and customers' feedbacks and suggestions.

See [docs.exegol.com](https://docs.exegol.com/) for more information.

## Layout

| Path | Role |
|------|------|
| `triggers/` | When to fire |
| `actions/` | What to collect |
| `profiles/demo.yml` | Wires the demo rules |

## Demo profile (`demo`)

1. **Kerberos Pass-the-Ticket**: **IF** Impacket style tools or `evil-winrm-py` with `-k`/`--kerberos` and `KRB5CCNAME` set, **THEN** dump the ccache file.
2. **Network traffic**: **IF** `Responder` or `bettercap`, **THEN** network capture for the process lifetime.
