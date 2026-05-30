# Hackathon Submission Packet

## Project Name

Qdrant Reward Route Radar

## Short Description

A non-chatbot Qdrant vector-search dashboard that ranks high-upside reward opportunities by semantic fit, payout size, risk, and safety constraints, while blocking routes that require social accounts, wallet signing, or internal instruction disclosure.

## Repository

https://github.com/xordanx/qdrant-reward-route-radar

## Demo Video

https://github.com/xordanx/qdrant-reward-route-radar/blob/main/rewardops_guard/delivery_kits/qdrant_reward_radar/demo_video/renders/qdrant_reward_route_radar_demo.mp4

## Package Path

`rewardops_guard/delivery_kits/qdrant_reward_radar`

## What It Does

Reward Route Radar indexes synthetic reward opportunities in Qdrant, converts each route into a deterministic local vector, and combines vector similarity with payload filters for reward amount, risk, and safety flags. The result is a ranked operator queue that surfaces viable high-value routes and excludes unsafe work.

## Why It Is Not A Chatbot

The interface is a dashboard and CLI ranking surface. The user changes search intent, minimum reward, maximum risk, and review-mode controls; Qdrant returns ranked routes. There is no chat transcript, no Q&A loop, and no hidden prompt dependency.

## How Qdrant Is Used

- Qdrant stores each opportunity as a vector point with structured payload.
- Vector search ranks opportunities by semantic fit to the operator's intent.
- Payload filters enforce hard gates for reward threshold, risk level, no social-account requirement, no wallet signing, and no secret disclosure.
- Review-mode routing keeps KYC/payment-document routes visible for human review without executing them automatically.

## Rule Compliance

- Qdrant is a material part of the project.
- The project is not a pure chatbot.
- The repository contains code, README, run instructions, tests, and dependencies.
- The demo video is 72 seconds, below the 3-minute limit.
- The dataset is synthetic and public.
- The app does not require user social accounts, wallet signatures, KYC, PHI, secrets, or internal agent instructions.

## Verification Commands

```bash
python3 -m venv /tmp/qdrant-radar-venv
/tmp/qdrant-radar-venv/bin/python -m pip install -r rewardops_guard/delivery_kits/qdrant_reward_radar/requirements.txt
/tmp/qdrant-radar-venv/bin/python -m unittest rewardops_guard.delivery_kits.qdrant_reward_radar.test_reward_radar -v
/tmp/qdrant-radar-venv/bin/python -m rewardops_guard.delivery_kits.qdrant_reward_radar.contest_preflight
```

## Contact / Team

Solo project under the GitHub account `xordanx`.

## Share Status

The repository is configured as public through GitHub API (`private=false`). If the form requests a direct video file rather than the GitHub preview page, use the MP4 path above from the repository.
