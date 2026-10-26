# ArtPose 3D

A biomechanical posing engine for artists. Pure JavaScript, single HTML file, zero dependencies.

I'm a draftsman. I built this to understand how the human body actually moves — which joints follow which, what a pose does to balance, where the limits are — so my drawings stay anatomically coherent.

## What it does

- **2-bone IK** for arms and legs (law of cosines) with hard anti-dislocation guards and anatomical ROM at every joint
- **Spine as two segments** with real flexion/extension and lateral bend
- **Ground contact as a constraint**: the foot detects its lowest point, computes a corrected ankle target, and the IK re-solves the leg in one deterministic pass
- **Balance check**: center-of-mass projection onto the support region (convex hull, monotone chain) — classified as point / segment / polygon
- **Custom 3D-to-SVG renderer** with depth sorting and shadows
- **Keyframe animation** + procedural walk/run cycles
- **Post-solve validator**: checks every rigid segment length and joint for NaN/disarticulation

## Run it

Open `index.html` in a browser. That's it. No build, no install.

## Why

Existing 3D posers are either closed, heavy, or can't tell you whether a pose is *physically holdable*. I wanted a lightweight tool that not only poses the body but verifies it stands — ground contact, center of mass, joint limits.

## Status

Functional engine, mobile-first UI, several preset poses. In progress: export, text-to-pose generation.
