# Natural Language Pose & Costume Prompts

**English** | [简体中文](README.zh-CN.md)

## Credits and References

- Reference gallery creator: [ギア / @giaaibusi](https://x.com/giaaibusi)
- Costume references: [AI Costume Gallery / COSTUME-DB-01](https://ai-costume-gallery.pages.dev/)
- Pose references: [AI Pose Gallery / POSE-DB-01](https://ai-pose-gallery.pages.dev/)

Thank you to the original creator for providing the costume and pose reference galleries. This project is not affiliated with or endorsed by the creator or any image generation model or platform. Attribution does not imply that the creator has authorized this project.

## About

English natural-language descriptions of poses and costumes for image generation models and tools that support natural-language prompts. They are not tied to a specific model. Use them on their own, combine them with other prompts, or pair them with character LoRAs. This repository contains TXT captions and documentation, plus documentation screenshots in `assets/Preview.png` and `assets/preview2.png`. It does not include the downloadable source image dataset or an image index.

These descriptions were written by observing reference images. They are not the original creator's generation prompts or official prompt exports from any model or platform. Materials are described according to their visible appearance.

## Preview

![Pose gallery page preview](assets/Preview.png)

Gallery-page screenshot supplied for documentation preview; source: [AI Pose Gallery](https://ai-pose-gallery.pages.dev/).

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

### Caption File Locations

Open a category subfolder inside `姿势图库_POSE_1439/` or `服装图库_COSTUME_1407/` to find the TXT captions. Keep each locally obtained reference image next to its matching caption, with the same filename stem:

```text
category-folder/
├── full_sexy_P001_front.png   # local reference image
└── full_sexy_P001_front.txt   # matching caption
```

![Local images beside matching TXT captions](assets/preview2.png)

The screenshot illustrates the local folder layout. Reference images are not included in the caption folders in this repository.

### ChatGPT: Character + Costume + Pose References

In a ChatGPT conversation with image generation available, attach three reference images and explain each image's role:

1. **Character image**: the character's identity and appearance.
2. **Costume image**: the clothing, colors, and accessories to use.
3. **Pose image**: the body position, camera angle, and framing to follow.

You can also paste the matching costume and pose captions to clarify details. Example prompt:

```text
Generate a new image using these references:
Image 1 defines the character. Preserve the character's recognizable appearance.
Image 2 defines the outfit. Use its clothing, colors, and accessories.
Image 3 defines the pose. Follow its body position, camera angle, and framing.
Costume details: [paste costume caption]
Pose details: [paste pose caption]
Scene and lighting: [describe the environment and lighting]
```

Review the result and request targeted changes as needed. Reference matching is not guaranteed. See [OpenAI's image generation guide](https://learn.chatgpt.com/docs/image-generation) for using multiple reference images.

### ComfyUI: Character LoRA Prompt + Caption + Environment and Lighting

Load a character LoRA compatible with your base model using your workflow's LoRA loader. In the positive prompt / text-encoding node, combine:

```text
[character LoRA trigger words and character description]
+ [costume caption]
+ [pose caption]
+ [environment and lighting]
```

The `+` signs show how to combine the parts; replace the placeholders with actual text and join them into a coherent prompt. Use one or both caption types as needed. Example:

```text
my_character, an adult woman with short black hair.
An ivory knit top with a pink pleated miniskirt and white sneakers.
Standing with one hand on the hip, head slightly tilted, three-quarter view, full-body framing.
On a quiet garden path, soft late-afternoon sunlight, gentle shadows.
```

Replace `my_character` with your LoRA's actual trigger. Trigger words alone do not load a LoRA: select and connect it in the workflow, then adjust its strength as needed. Adapt caption length and wording to your model.

## Reference Images and Download Rules

**The source websites prohibit redistributing, reposting, or reselling their images, including original-resolution and edited images. The downloadable source image dataset is not included; the documentation previews show the gallery page and a local folder layout. Publishing these text captions does not grant permission to redistribute the images.**

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

## Next Step: A Local HTML Gallery for Personal Browsing

Once you have obtained reference images in accordance with the source websites' permissions and paired them with the captions, an agent with local file and coding capabilities can build a simple HTML gallery for your personal browsing. This is an optional local workflow, not a gallery application included in this repository.

Replace the folder placeholder below with your local collection's root folder, then give this prompt to your agent:

```text
Build a simple local HTML gallery for my pose and costume reference collection.

Collection folder: [absolute path to my local pose and costume folders]

Use only images and TXT captions already present on my computer. Do not download anything, modify the originals, upload files, or publish the gallery.

Scan the category subfolders and pair images with TXT captions by their relative folder and filename stem. Support PNG, JPG/JPEG, and WebP. Preserve Unicode filenames and handle spaces in paths. If a caption has no image, show a text-only card; if an image has no caption, show a clear missing-caption label. Keep caption variants as separate entries rather than guessing their matching image.

Create a responsive thumbnail grid with lazy loading or pagination. Add filters for pose/costume and category, plus search by filename/ID and caption text. Clicking a card should open a larger image and the full caption, with a Copy Caption button and previous/next navigation. Mark NSFW entries using existing folder or filename labels and keep them hidden by default, with a manual toggle to show them.

Use plain HTML, CSS, and JavaScript, with no external CDN, analytics, API keys, or cloud services. Read captions as plain text and escape filenames and caption content when displaying them. Use relative image paths and keep the originals in place.

Prefer a generated local index with embedded caption data so index.html can be opened directly. If browser restrictions require a local server, provide a minimal launcher bound only to 127.0.0.1 and clear start/stop instructions. Make the Copy Caption button work in the chosen mode, with a manual-copy fallback.

Save generated files in a separate local-gallery folder. Verify that several image/caption pairs display correctly and that filtering, search, navigation, and copying work. Report image, caption, paired, and unmatched counts, then tell me exactly how to open the gallery. Keep all images and gallery data local; do not add them to Git or publish them.
```
