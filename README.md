# Natural Language Pose & Costume Prompts

**English** | [简体中文](README.zh-CN.md)

## Credits and References

- Reference gallery creator: [ギア / @giaaibusi](https://x.com/giaaibusi)
- Costume references: [AI Costume Gallery / COSTUME-DB-01](https://ai-costume-gallery.pages.dev/)
- Pose references: [AI Pose Gallery / POSE-DB-01](https://ai-pose-gallery.pages.dev/)

Thank you to the original creator for providing the costume and pose reference galleries. This project is not affiliated with or endorsed by the creator or any image generation model or platform. Attribution does not imply that the creator has authorized this project.

## About

English natural-language descriptions of poses and costumes for image generation models and tools that support natural-language prompts. They are not tied to a specific model. Use them on their own, combine them with other prompts, or pair them with character LoRAs. This repository contains only TXT captions and documentation, with no images, thumbnails, or image indexes.

These descriptions were written by observing reference images. They are not the original creator's generation prompts or official prompt exports from any model or platform. Materials are described according to their visible appearance.

## Contents and NSFW Notice

- `姿势图库_POSE_1439/`: 1,714 TXT files, including caption variants from the original local collection. The number 1439 is part of the reference collection's name.
- `服装图库_COSTUME_1407/`: 1,407 TXT files, organized by costume category and retaining the original IDs.

**The two-person pose prompts include NSFW (adult) content. Review and select prompts yourself, use them responsibly, and follow applicable laws and the rules of your chosen platform.**

## How to Use

Choose a TXT file by ID and use its text directly as a prompt, or combine it with a character description. Add a scene, lighting, and framing as needed. If you use a character LoRA, include its trigger words as required by your model.

The captions use ordinary English rather than specialized tags or model-specific syntax. They can serve as prompt material for any image generation tool that supports natural language. Interpretation and visual fidelity vary by model, so adjust wording and length as needed.

Pose descriptions follow this order:

Body Position → Legs → Arms → Torso → Head → Camera Angle → Framing

Costume descriptions cover visible colors, cuts, materials, and accessories without binding them to a particular character identity.

## Reference Images and Download Rules

**The source websites prohibit redistributing, reposting, or reselling their images, including original-resolution and edited images. This repository provides no images. Publishing these text captions does not grant permission to redistribute the images.**

As of October 30, 2026, both source websites also explicitly prohibit bulk downloading, including automated retrieval with tools. They allow individual images to be used as generation references under their stated terms. Free use does not mean permission to bulk download or redistribute. Always check the source websites for their latest terms.

Images obtained individually in accordance with the source websites' permissions can be placed locally in the corresponding caption folders. Match each image's filename to its TXT caption, changing only the extension—for example, `SPR-0001.png` and `SPR-0001.txt`. Keep images local and do not commit them to this repository. The `.gitignore` restricts which file types are tracked.

### Organizing Images with an Agent

If your chosen agent, such as Codex, Muse, or Grok, supports local file operations, you can ask it to organize images you have already obtained with permission. For example:

> Organize the pose and costume images I have obtained in accordance with the source websites' permissions into the corresponding TXT caption folders by ID. Keep each image and caption under the same filename, and do not upload or redistribute the images.

**Use the following instruction only after obtaining explicit permission from the creator to bulk download. It is not permitted under the source websites' current default terms:**

```text
download all pose costume images from https://ai-costume-gallery.pages.dev/ and https://ai-pose-gallery.pages.dev/
```

Check your agent's network, download, and local file capabilities, as well as any service fees, before using it.
