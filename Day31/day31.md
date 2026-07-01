# Control Tower — AI Supply Chain Simulation

A single-file, browser-based simulation game where you play Head of Operations for a global supply chain company. Alerts stream in, KPIs move in real time, and every decision has a consequence.

No build step, no dependencies, no internet connection required — just open the HTML file.

## How to Run

1. Download `control-tower.html`.
2. Double-click it (or open it via **File → Open** in any modern browser).
3. Click **Start Shift**.

Works fully offline. Tested in Chrome, Firefox, Safari, and Edge.

## Gameplay

You have **3 minutes** to keep the network running.

- Alerts appear on the left with a title, description, priority, and countdown.
- Each alert offers 3–4 actions. One is usually the strongest operational call — others are trade-offs, and some are traps.
- **Delay Decision** buys time but slightly worsens the situation, and triggers a follow-up alert a few seconds later.
- **Ignore** (or letting an alert's timer run out) is always the worst outcome.
- Alert frequency increases as the clock runs down, and multiple alerts can be active at once.

At the end of the shift you get a performance grade (A+ to D), a written summary, and a full KPI breakdown.

## KPIs

| KPI | What it measures |
|---|---|
| Service Level | % of orders fulfilled on time |
| Customer Satisfaction | Client sentiment |
| Inventory Health | Stock accuracy and buffer |
| Transportation Efficiency | Fleet and routing performance |
| Operating Cost | Cost index — **lower is better** |
| Revenue Protected | Value saved from disruption |
| Score | Overall performance score |

## Alert Types

Port Congestion · Supplier Delay · Truck Breakdown · Warehouse Running Out of Stock · Customs Inspection · Demand Spike · Factory Machine Failure · Weather Disruption · Wrong Inventory Count · Damaged Shipment

## Controls

| Control | Effect |
|---|---|
| 🔊 / 🔇 | Toggle sound (visual indicator only — no audio) |
| ⏸ / ▶ | Pause / resume the shift |
| ? | Open instructions |
| Play Again | Reset and start a new shift |

## Tech

- Single `.html` file — HTML, CSS, and vanilla JavaScript only
- No frameworks, no external libraries, no APIs, no backend
- Responsive layout for desktop and mobile

## File

- `control-tower.html` — the entire application
