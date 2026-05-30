# Qdrant Reward Route Radar

Standalone public repository for the Qdrant "Think Outside the Bot" 2026 virtual hackathon.

Reward Route Radar is a non-chatbot Qdrant application that indexes reward opportunities, embeds them with deterministic local feature vectors, and uses Qdrant vector search plus payload filters to rank high-upside routes while blocking unsafe work such as social-account requirements, wallet signing, or secret disclosure.

## Hackathon Fit

- Uses Qdrant as the material vector index and payload filter engine.
- Presents an operator ranking surface, not a conversational Q&A bot.
- Demonstrates vector search for reward-route triage, risk filtering, and payout-focused prioritization.
- Uses a synthetic public dataset; no private account data, social accounts, wallet signatures, PHI, or secrets are required.

## Run The Demo

```bash
python3 -m venv /tmp/qdrant-radar-venv
/tmp/qdrant-radar-venv/bin/python -m pip install -r rewardops_guard/delivery_kits/qdrant_reward_radar/requirements.txt
/tmp/qdrant-radar-venv/bin/python -m rewardops_guard.delivery_kits.qdrant_reward_radar.reward_radar --min-reward 1000 --allow-review --json
/tmp/qdrant-radar-venv/bin/python -m rewardops_guard.delivery_kits.qdrant_reward_radar.contest_preflight
```

Start the local web demo:

```bash
/tmp/qdrant-radar-venv/bin/python -m rewardops_guard.delivery_kits.qdrant_reward_radar.web_demo --host 127.0.0.1 --port 8787
```

Then open `http://127.0.0.1:8787`.

## Demo Video

- MP4: `rewardops_guard/delivery_kits/qdrant_reward_radar/demo_video/renders/qdrant_reward_route_radar_demo.mp4`
- Manifest: `rewardops_guard/delivery_kits/qdrant_reward_radar/demo_video/VIDEO_MANIFEST.md`
- Contact sheet: `rewardops_guard/delivery_kits/qdrant_reward_radar/demo_video/renders/qdrant_reward_route_radar_contact_sheet.png`

The rendered MP4 is 72 seconds, under the 3-minute limit.

## Tests

```bash
/tmp/qdrant-radar-venv/bin/python -m unittest rewardops_guard.delivery_kits.qdrant_reward_radar.test_reward_radar -v
```

Dependency-free checks still run with system Python. Qdrant integration tests require `qdrant-client` from `requirements.txt`.

## Submission Packet

See `HACKATHON_SUBMISSION.md` for copy-ready form fields, links, and rule-compliance notes.
