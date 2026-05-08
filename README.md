# ChipBuddy 🛠️

Conservative feeds & speeds for trainee machinists. Live at **[chipbuddy.org](https://chipbuddy.org)**.

## What it is

A single-page web tool that gives you safe starting numbers for CNC milling and drilling. No login, no ads, no tracking. Aluminum-only in v1; steel, stainless, copper, and brass are next.

Punch in your tool, your machine's max RPM, and how rigid your setup feels. Slide between Conservative → Pro to see how the numbers shift. Always verify by chip color, sound, and feel — **these are starting points, not guarantees.**

## Cut types supported

- **Pocket / Adaptive Clearing** — heavy chip removal
- **Facing** — skim the top of stock flat
- **Contour** — finish the wall around a part
- **Drilling** — peck cycle (G73 chip-break + G83 full-retract)

## Safety rules baked in

- Spindle never recommended above your machine's max
- Tools ≥ 1/8" auto-cap at 6000 RPM (override if you want)
- Axial DOC capped by tool flute length
- Pocket warnings if you select 4+ flutes for cuts deeper than 1× tool diameter (chip-evac risk)
- Pro mode shows a "verify on test cut" reminder

## Built by

Thad — message **@axiradthad** on i3 Detroit Slack.

> *"I've had great pleasure over the last 10 years of training all experience level of users to bring their creations to life in this zone, and from that experience created this tool. Have a blast, stay curious, have fun and of course be safe. :)"*

## Run locally

It's one HTML file. Clone the repo, double-click `index.html`. That's it.

```sh
git clone https://github.com/axirad/chipbuddy.git
cd chipbuddy
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

## Tuning the numbers

All lookup tables (SFM, IPT, DOC multipliers, rigidity penalties) live as JavaScript constants at the top of the `<script>` block in `index.html`. Edit, refresh, see results instantly. No build step.

## License

MIT — see [LICENSE](LICENSE). Use it, fork it, ship it. Just don't blame me if you crash a tool.

## Contributing

Found a number that's off, want a material added, hit a bug? Message me on i3 Slack.
