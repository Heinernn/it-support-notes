# Network troubleshooting

I work from the bottom up, one layer at a time, and I write down what I find. Most "the internet is down" tickets
are solved in the first three steps.

## 1. Is it just this user?

Ask whether other people or other devices on the same network are affected. If everybody is down, the problem is
the router, switch or the provider, not the user's computer.

## 2. Physical and link

- Cable plugged in at both ends? Link light on the port? Try another cable or port.
- Wi-Fi: is the adapter enabled, airplane mode off, and is the user on the right network?

## 3. IP configuration

Windows:

```
ipconfig /all
```

Linux:

```
ip addr
ip route
```

What to look for:

- An address that starts with **169.254.x.x** means the computer did not get an address from DHCP.
- A correct address, subnet mask, **default gateway** and DNS servers.
- To renew on Windows: `ipconfig /release` and then `ipconfig /renew`.

## 4. Reach the gateway, then the internet

```
ping <default gateway>
ping 8.8.8.8
ping example.com
```

| Result | Likely cause |
|--------|--------------|
| Gateway fails | Local network problem (cable, Wi-Fi, switch, wrong IP) |
| Gateway works, `8.8.8.8` fails | Router or provider problem |
| `8.8.8.8` works, name fails | **DNS** problem |

## 5. DNS

```
nslookup example.com
```

Try another DNS server to confirm. On Windows, `ipconfig /flushdns` clears the local cache.

## 6. Where does the traffic stop?

```
tracert example.com      (Windows)
traceroute example.com   (Linux)
```

## 7. Software in the middle

- Firewall or antivirus blocking the application.
- A VPN or proxy configured by mistake.
- Wrong date and time on the computer (breaks HTTPS and logins).

## 8. Close the ticket properly

- Confirm with the user that it works.
- Write down the cause and the fix in the ticket.
- If it needs a change on the network equipment, escalate with the output of the commands above.
