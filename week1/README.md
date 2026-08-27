# CTS1380 Week 1 interactive topic artifacts

Four standalone HTML files, one per topic. Each is completely self-contained: stylesheet, GSAP,
the practice console engine, and the topic script are all inlined. There are no shared assets and
no build step, so any file works on its own from any URL, and from local disk.

CBT Technology Institute, Flagler Campus. Prof. Luis De Leon.

| File | Topic | Session |
|---|---|---|
| `w1s1-vlans.html` | 1.1 Building your first VLANs | W1S1 |
| `w1s2-management-voice.html` | 1.2 Management VLAN, SVI, and voice VLAN | W1S2 |
| `w1s3-two-switches.html` | 1.3 One VLAN across two switches | W1S3 |
| `w1s4-persistence-audit.html` | 1.4 Persistence, audits, and multi-fault troubleshooting | W1S4 |

## What students actually do

Every file contains a practice console that accepts real IOS syntax for the Week 1 command set and
rejects everything else the way a switch would. The topology and status panels redraw from the live
configuration, and the task list ticks itself off as each requirement is met. Nothing is scored and
nothing is sent anywhere; the state lives in the page and resets with the button.

- **1.1** Configure two VLANs from an empty switch, then send a broadcast that follows your own
  configuration and run a connectivity test scored against the design requirement.
- **1.2** Bring a management interface up through its real states, including up-with-protocol-down,
  ping it, then add a voice VLAN and watch the phone's frame change destination.
- **1.3** Two switches, two consoles, one fault left by a contractor. Reproduce the complaint,
  compare both ends of each link, fix it, then explore what one cable per VLAN costs at scale.
- **1.4** Save, erase, reload, and delete vlan.dat on a live switch while three memory panels track
  where each piece of the configuration is stored. Then audit a configuration against a
  requirements document and find four discrepancies.

Each file closes with three self-check questions that give per-answer feedback and map to the
Week 1 quiz.

## Deploying and embedding

1. Push the four files to your repository and enable GitHub Pages.
2. In the Canvas page, click the `</>` icon to open HTML view and paste:

```
<p><iframe style="width: 100%; height: 2200px; border: 1px solid #dce9f5;"
   title="CTS1380 Topic 1.1" loading="lazy"
   src="https://USERNAME.github.io/REPO/w1s1-vlans.html"></iframe></p>
<p><a href="https://USERNAME.github.io/REPO/w1s1-vlans.html" target="_blank" rel="noopener">Open this page in a new tab</a></p>
```

A cross-origin iframe cannot resize itself, so the height is fixed. 2200px suits a desktop; the
frame scrolls internally below that. Always keep the new-tab link underneath, which is what most
students on phones will use.

If your Canvas admin has Content Security Policy enabled under Settings, Security, add
`USERNAME.github.io` to the allowed domains or the frame renders blank. Test one page first.

After updating a file, append a version query to the iframe source, for example `?v=2`, so students
receive the new copy rather than a cached one.

## Accessibility

Console output and status lines are `aria-live` regions, every control is keyboard operable, and
`prefers-reduced-motion` is honoured, with animations resolving instantly while the text still
updates. Nothing is conveyed by motion or colour alone: every state change is also stated in words.

## Licensing

GSAP 3.15.0 is by GreenSock, bundled under the GSAP standard license rather than pulled from a CDN,
so the pages work with no external requests at all.
