# Deluge ↔ Ableton Converter

Convert songs between **Synthstrom Deluge** and **Ableton Live** — in both directions.

---

## What it does

- **Deluge → Ableton:** Turn a Deluge song (`.XML`) into an Ableton Live Set (`.als`). Your audio tracks, MIDI, clips, and tempo come across.
- **Ableton → Deluge:** Turn an Ableton Live Set into a Deluge song. Audio and MIDI clips, arrangement, and tempo are converted for the Deluge.

You get a **desktop app** (Mac) with two tabs—one for each direction—plus file pickers and one‑click conversion.

---

## Download and install

1. Go to [Releases](https://github.com/solaris76/deluge-to-ableton-release/releases) and download the latest **DMG** for your Mac (Apple Silicon only currently).
2. Open the DMG and drag **Deluge ↔ Ableton** into **Applications**.

**Before first launch:** macOS often blocks downloaded apps. If you see **" damaged and can't be opened"** or **"unidentified developer"**, the app is fine — macOS is blocking it. Open **Terminal** and run:
   ```bash
   xattr -cr "/Applications/Deluge ↔ Ableton.app"
   ```
   Then open the app as usual. You only need to do this once after installing.
   
---

## How to use

1. Open **Deluge ↔ Ableton**.
2. Choose a tab:
   - **Deluge → Ableton:** Pick a Deluge `.XML` file, choose an output folder, then **Convert**.
   - **Ableton → Deluge:** Pick an `.als` file, choose an output folder (e.g. your Deluge `SONGS` folder), then **Convert**.
3. Use the new file in Ableton or on the Deluge as usual.

Song name is optional; it’s guessed from the filename if you leave it blank.

---

## What gets converted

| | Deluge → Ableton | Ableton → Deluge |
|---|------------------|------------------|
| **Tempo** | Yes | Yes |
| **Audio clips** | Yes | Yes |
| **MIDI notes** | Yes | Yes |
| **Session view / scenes** | Yes | Yes |
| **Arrangement / timeline** | Yes | Yes |
| **Track names & colors** | Yes | Yes |

**Not converted:** synth patches, effects, automation, swing. The app moves **musical content** (tracks, clips, notes, tempo), not sound design.

---

## Before you convert

**Ableton → Deluge:**

- **Bounce or freeze** clips that use heavy warping, effects, or complex warping so they’re plain audio.
- **Warp loops** to your project tempo, then consolidate, so they match the BPM on the Deluge.
- Keep **samples in the project’s Samples folder** so the converter can find them.

**Deluge → Ableton:**

- Use **Collect media** on the Deluge so all samples are with the song. The converter looks for those files when creating the ALS.

---

## Tips

- **Deluge → Ableton:** Use "Include arrangement view" if you want the timeline, not only session view.
- **Ableton → Deluge:** Use 44.1 kHz audio when you can; the Deluge handles it best.
- **BPM in filenames:** Names like `loop_120bpm.wav` help the converter set warping correctly (Deluge → Ableton).

---

## Troubleshooting

**"Audio files not found"**  
Keep Ableton samples in the project’s `Samples` folder. For Deluge songs, use **Collect media** before converting.

**Clips or timing seem wrong**  
Check tempo in the *source* project. For warped clips, consolidate at project tempo before converting to Deluge.

**"MIDI can’t convert to Kit" on Deluge**  
The Deluge won’t change a clip with notes into a Kit. Workaround: create an empty Kit track, then copy/paste the notes.

**Volume too loud on Deluge**  
Deluge outputs can distort. Lower track levels in the Deluge after conversion if needed.

---

## System requirements

- **Mac** (macOS 10.12 or later), Apple Silicon or Intel.  
- **Windows** support is planned for a later release.

---

## Support the project

If the app is useful to you, you can [support development via PayPal](https://paypal.me/cgsolaris).

---

## License

This converter uses Ableton’s ALSExportKit; see `ALSExportKit-1.8/ALSExport_License_v2.0.pdf` for its terms.

---

*For build instructions and developer documentation, see the `docs/` folder and the project wiki.*
