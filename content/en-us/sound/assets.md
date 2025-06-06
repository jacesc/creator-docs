---
title: Audio assets
description: Explore how to find and import audio assets for use in your experiences.
---

You can [find](#find-assets) a wide variety of free‑to‑use audio assets in the [Toolbox](../projects/assets/toolbox.md), or you can [import](#import-audio) audio assets that you're certain you have permission to use, such as audio files you make yourself. The [asset privacy](../projects/assets/privacy.md) system automatically ensures that the IDs of your imported audio can't be accessed by users without the proper permissions.

## Find assets

The [Toolbox](../projects/assets/toolbox.md) contains a wide variety of audio assets made by Roblox and the Roblox community for creators to use within their experiences, including more than 100,000 professionally-produced sound effects and music tracks from top audio and music partners.

1. Navigate to the **Creator Store** tab of the [Toolbox](../projects/assets/toolbox.md), then use the category selector dropdown to select **Audio**.

   <img src="../assets/studio/toolbox/Creator-Store-Audio.png" width="360" alt="Audio section of Creator Store in Studio's Toolbox" />

2. Use the keyword search, quick filter options, and/or advanced filters to narrow down the results.

   <img src="../assets/studio/toolbox/Creator-Store-Audio-Discovery.png" width="580" alt="Audio discovery options in Studio's Toolbox" />

3. Click any audio asset to insert it as a new `Class.Sound` instance into the [Explorer](../studio/explorer.md) window. You can also click the small **play** button to begin previewing it and to view more info.

   <img src="../assets/studio/toolbox/Audio-List-Preview.png" width="360" alt="Audio asset preview button in Studio's Toolbox" />

	<Alert severity="info">
	See [Sound Objects](../sound/objects.md) for details on how to use `Class.Sound` instances in an experience.
	</Alert>

## Import audio

You can import custom audio as long as it meets the following requirements:

- You have the legal rights to that asset.
- It adheres to the [Community Rules](https://en.help.roblox.com/hc/articles/203313410) and [Terms of Use](https://en.help.roblox.com/hc/articles/115004647846).
- It's a single track/stream in either `.mp3`, `.ogg`, `.wav` or `.flac` format.
- It's less than 20 MB in size and 7 minutes in duration.
- Its sample rate is less than or equal to 48 kHz.
- Its channels are set to mono or stereo 2.0, 3.0, or 5.1 surround.

If you're [ID verified](../production/publishing/account-verification.md), you can import 100 free audio assets per 30 days; if you're unverified, you can import 10 free audio assets per 30 days. Studio assigns each new audio asset a **unique asset ID** that you can use within your experiences to [play the audio](../sound/objects.md).

You can import audio through the [Asset Manager](../projects/assets/manager.md), the [Creator Dashboard](https://create.roblox.com/dashboard/creations), or the [Open Cloud API](../cloud/guides/usage-assets.md). To import audio through the **Asset Manager**:

1. Click the **Import** button.
1. Select and then confirm the audio files you want to import from your local system.
1. Once you confirm the imports and the files import successfully, they display with a green checkmark and a completed status.

   <Alert severity="info">
   To standardize the playback format and check for corrupt or invalid files, Studio transcodes imported audio before saving it as an asset. If you receive an error while importing audio, Studio is likely rejecting it during the transcode process. In addition, some older audio tools generate invalid file headers or frames when exporting.

   If Studio continues to reject the audio you're trying to import, ensure your audio tools are updated, then verify that the audio files meet the import requirements.
	</Alert>

The audio assets are now within the moderation queue. Although you are initially the only one who can view and use private audio assets, the [asset privacy](../projects/assets/privacy.md) system lets you grant usage permissions to specific friends and experiences.
