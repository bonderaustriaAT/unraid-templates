# JustDNS Unraid templates

[Unraid Community Applications](https://ca.unraid.net/) template for
[**JustDNS**](https://github.com/bonderaustriaAT/JustDNS), a self-hosted filtering
DNS resolver with a company-level privacy dashboard.

## What JustDNS does

JustDNS filters DNS for your whole network. It blocks ads, trackers and malware,
and its privacy dashboard shows which companies your devices actually contact, with
a per-device breakdown and a world map of where answers resolve. It ships encrypted
upstreams (DNS-over-TLS) by default, per-device and per-group policies, DNSSEC
validation, user accounts with roles and TOTP, and optional multi-node high
availability.

Full documentation lives in the main repository:
<https://github.com/bonderaustriaAT/JustDNS>.

## Install on Unraid

1. In Unraid, open the **Apps** tab and search for **JustDNS**.
2. Install the template. The defaults expose DNS on port 53 and the dashboard on
   port 8080.
3. Open the dashboard at `http://YOUR-UNRAID-IP:8080` and finish the first-run
   wizard.
4. Point your router's or devices' DNS at your Unraid server's IP.

### Notes

- The **Keys** volume (`/keys`) holds the at-rest encryption key. Back it up
  separately from the **Data** volume; losing it makes the sealed account and
  config files unreadable.
- Ports **80/443** are only for the optional custom block page and clash with
  Unraid's own web UI. They are off by default; map them to free host ports, or
  give the container its own IP, only if you enable the block page.
- Ports **853/8443** are only needed if clients talk to JustDNS over encrypted DNS
  (DoT/DoH).
- Update JustDNS from the Unraid **Docker** tab. The project's in-app one-click
  updater is not used in this template.

## Support

Issues and questions: <https://github.com/bonderaustriaAT/JustDNS/issues>

## License

JustDNS and this template are licensed under AGPL-3.0-or-later. See [LICENSE](LICENSE).
