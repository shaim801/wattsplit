<div align="center">

# ⚡ WattSplit

**Split a shared prepaid electricity meter fairly, down to the last kWh.**

[**Live demo →**](https://shaim801.github.io/wattsplit/)

![HTML](https://img.shields.io/badge/HTML5-0b2a1a?style=flat-square&logo=html5&logoColor=c9f5c8)
![CSS](https://img.shields.io/badge/CSS3-0b2a1a?style=flat-square&logo=css3&logoColor=c9f5c8)
![JavaScript](https://img.shields.io/badge/Vanilla_JS-0b2a1a?style=flat-square&logo=javascript&logoColor=c9f5c8)
![No dependencies](https://img.shields.io/badge/dependencies-none-c9f5c8?style=flat-square&labelColor=0b2a1a)

</div>

---

## About

Several flats share **one prepaid main meter**, and each flat has its own **sub-meter**. Everyone tops up together, so someone has to work out who owes what.

WattSplit does that maths for you. Enter the main meter and sub-meter readings from the start and end of a recharge cycle, and it shows the effective **৳ per kWh** and **exactly how much of the bill is yours**, based on the units your own sub-meter recorded.

## Features

- **Fair by usage:** every flat pays for the kWh it actually used.
- **Any number of sub-meters:** choose 1 to 6, and change it whenever your building changes.
- **Live rate:** see the ৳ per kWh update as you type.
- **Clear results:** a result window with a summary, a donut chart, a per-flat breakdown and the full working.
- **Mismatch warning:** tells you if the sub-meters don't add up to the main meter (common lights, a pump, line loss, or a wrong reading).
- **Counting up or down:** works whether your meter's reading increases or counts down.
- **New cycle in one tap:** the current readings become the previous ones for the next cycle.
- **Private by design:** everything stays in your browser. No server, no sign-up, nothing is uploaded.
- **Responsive and polished:** works on phones and desktops, with smooth animations and a reduced-motion fallback.

## How the maths works

```
Money spent   = Previous balance − Current balance
Rate per kWh  = Money spent ÷ Main meter kWh used
Your bill     = Your kWh used × Rate per kWh
```

Using the main meter's real spend means taxes, demand charges and tariff slabs are already included in the rate.

**Example**

| Step | Calculation | Result |
| --- | --- | --- |
| Money spent | 1,404.35 − 128.52 | ৳ 1,275.83 |
| Main meter kWh used | 2,199.84 − 1,980.45 | 219.39 kWh |
| Rate per kWh | 1,275.83 ÷ 219.39 | ৳ 5.8154 |
| Your bill | 26.74 kWh × 5.8154 | **৳ 155.50** |

## How to use it

1. **Right after a recharge**, note the main meter's reading and balance, and every sub-meter reading.
2. **When the balance runs low**, note all of them again.
3. Open WattSplit and click **Calculate your bill**.
4. Enter the **previous** and **current** main meter reading and balance.
5. Choose how many sub-meters are on your main meter, then enter each flat's previous and current reading. Only your own flat is required.
6. Review, then click **Calculate my bill**.
7. When you recharge again, tap **Start new cycle** so the last readings carry over.

## Run it locally

There is no build step. It is a single file.

```bash
git clone https://github.com/shaim801/wattsplit.git
cd wattsplit
```

Then open `index.html` in your browser. Custom fonts load from Google Fonts, so they need an internet connection. Without one, the page falls back to system fonts.

## Deploy with GitHub Pages

1. Push `index.html` to the root of a public repository.
2. Go to **Settings → Pages**.
3. Set **Source** to *Deploy from a branch*, then choose `main` and `/ (root)`.
4. Wait a minute or two. The site goes live at `https://<username>.github.io/<repo-name>/`.

## Tech

- Plain **HTML, CSS and JavaScript**. No frameworks, no libraries, no build tools.
- Typography: [Bricolage Grotesque](https://fonts.google.com/specimen/Bricolage+Grotesque), [DM Sans](https://fonts.google.com/specimen/DM+Sans) and [Space Mono](https://fonts.google.com/specimen/Space+Mono).
- Page-to-calculator transition uses the **View Transitions API**, with a plain fade as a fallback.
- Readings are saved with `localStorage`.

## Project structure

```
wattsplit/
├── index.html   # the whole site: homepage + calculator
└── README.md
```

## Roadmap

- [ ] History of past cycles
- [ ] Optional fixed charges and common-area split
- [ ] Export or share the result as an image
- [ ] Bengali language option

## Author

Built by [**shaim801**](https://github.com/shaim801).

If WattSplit saved you an argument, a ⭐ on the repo is always appreciated.
