# cat-setting-harmony

## Overview

`cat-setting-harmony` is a scalar function that evaluates the holistic harmony of a cat photograph. It produces a score between 0 and 1 reflecting whether the lighting, background, and spatial composition of a photograph work together to create a coherent, inviting visual experience — or whether they pull in conflicting directions, undermining the image despite any individual strengths.

This function does not evaluate lighting quality or background cleanliness on their own. It evaluates the relationship between them. A photograph where both lighting and background are merely adequate but exist in beautiful agreement will outscore one where lighting is excellent but the environment undermines it. The central question is: does this photograph feel like a place where a cat can be seen and appreciated?

## Input

The function accepts a single required field:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `photo` | `image` | Yes | A photograph containing a cat in a visual setting. |

The photograph may be taken indoors or outdoors, in natural or artificial light, with any type of background. The only requirement is that a cat is present within a visual setting. No metadata, camera information, or additional context is needed — the function evaluates the image exactly as a human viewer would encounter it.

## Output

A scalar score in the range `[0, 1]`:

- **Scores near 1.0** indicate strong harmony — light, environment, and the cat as subject cooperate seamlessly to produce a unified, inviting scene.
- **Scores near 0.5** indicate partial harmony — the elements are neither fully cooperating nor fully clashing, with some tensions present.
- **Scores near 0.0** indicate disharmony — the visual elements conflict with one another, producing a disjointed or unwelcoming scene.

The final score is the weighted average of three internal evaluation tasks, each targeting a distinct quality of harmony.

## What It Evaluates

The function assesses three perceptual qualities that together determine whether a photograph achieves the feeling of wholeness:

### 1. Visual Unity

Whether the lighting, color temperatures, and environment are telling the same visual story. This is the foundation of harmony: do all elements of the frame cooperate to create a single coherent mood and sense of place, or do they pull in conflicting directions?

**Scores highly when:**
- Warm light falls across a setting that shares its warmth and tone
- Color temperatures are consistent across the scene
- The viewer's eye moves through the frame without encountering contradictions

**Scores poorly when:**
- Harsh, cool light clashes with a warm, cozy background
- Soft, intimate surroundings are disrupted by sharp, unflattering shadows
- The elements of the photograph feel like separate moments forced into the same frame

### 2. Subject Belonging

Whether the cat appears to naturally inhabit its setting rather than being marginalized or treated as an afterthought. A harmonious photograph presents the cat as the welcomed center of the scene — a creature that looks like it has chosen its place within the environment.

**Scores highly when:**
- The composition centers on the cat naturally
- The setting feels like it was made for the cat, or the cat for the setting
- The frame respects the cat as its primary subject

**Scores poorly when:**
- The cat is squeezed into a corner while empty or distracting space dominates
- The environment is so vast, cluttered, or visually loud that the cat becomes incidental
- The composition treats the cat as an object placed into a scene rather than a creature inhabiting one

### 3. Warmth of Invitation

Whether the overall mood of the photograph draws the viewer in with quiet welcome or holds them at a distance. This is the emotional register of the image — the feeling it creates when color palette, atmosphere, and the interplay of living cat with surroundings are taken together.

**Scores highly when:**
- The colors, atmosphere, and scene create a warm, hospitable feeling
- The image feels lived-in and alive
- The viewer wants to stay and look a little longer

**Scores poorly when:**
- The scene feels cold, sterile, or emotionally flat
- The cat's living warmth is dampened by unwelcoming or clinical surroundings
- Color temperatures are harsh, institutional, or devoid of comfort

## Use Cases

- **Content curation and ranking**: Surface the most visually harmonious cat photographs from large collections, prioritizing images that feel whole over those that are merely technically competent.
- **Pet photography platforms**: Help users find and appreciate the best images by ranking photographs based on the coherence and appeal a human viewer actually experiences.
- **Photographer feedback**: Provide photographers with a score reflecting whether the scene they captured holds together as a unified moment — a quality that is difficult to self-assess.
- **Image dataset filtering**: Build high-quality datasets for calendars, social media, advertising, or visual products by filtering for photographs people will genuinely want to look at.
- **Recommendation systems**: Distinguish photographs that merely contain a cat from photographs that present a cat beautifully, enabling more appealing recommendations.

## Scoring Philosophy

This function is built on the conviction that the whole of a photograph matters more than any of its parts. It captures the emergent quality that arises when light and environment cooperate — or the tension that appears when they do not. People do not experience photographs by evaluating lighting first, then background, then composition, and adding the scores together. They see a moment, and they feel whether it coheres. `cat-setting-harmony` honors that reality by evaluating the moment itself.
