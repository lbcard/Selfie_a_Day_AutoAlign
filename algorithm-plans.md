# This is the general plan and aims for this project

## Overall Aim

This project is to process selfie photos taken each day by sorting and aligning them, then producing videos based on parameters like how long the video should be or how many frames a photo is shown for.

## Current Project State

It is currently half created. It will process a folder full of photos based on metadata and use tools like openCV to assess the best image. It doesn't produce videos yet and some of the algorithms are basic.

Algorithms and logic can be rewritten if required or can be more efficient.

## Stack

The algorithms are currently written in python. This is fine but there are no strict requirements to keep it as python if a different language is better suited.

## Photo Logic

- only 1 photo per day, so if there are multiple photos for the day, then it should pick the best one (maybe based on focus? ideally focus of the person)
- photos should be aligned by the eyes of the person so they are all in the same place, then resized and cropped as necessary to the video output settings.
- the metadata of the image is the source of truth, not the file names.
- if a day is missing a photo but there are photos taken in the early hours of the morning the following day, then it is likely that I was just too late and these should be the images for the previous day so use them ONLY if there are images to use also for that current day (e.g. some more photos were taken later in the day). Use sensible judgement for this.
- Lighting and colours will be different as the photos were taken in different place with different cameras. The algoritim should try to balance photos a bit if necessary so the lighting and colours don't change a lot. Again, use sensible judgement for this.

Add any additional logic as required if anything could be done better or is missing.

## Features

- algorithm should be able to recursively work on a folder of images where images could be in any order.
- algorithm should copy all images to process so it doesn't change the originals.
- algortihm should produce a summary at the end in addition to the video. The summary should list useful stats like the amount of images processed, list and number of missing days, any errors, time period the photos cover, output video details (resolution, frame rate etc...), number of photos included in the video, number of photos rejected. This can just be a json report file.
- there should be a config file (maybe json?) that allows for setting the settings of the output video. Maybe it could be an array to be able to generate different videos during the same run.
- It would be great for output video settings to also include the option to add a small date text that the image is for so this can be seen in the video.

Add any features that are common in these types of programmes that might be useful.

## Photo sources

Photos will generally come from a local folder so there needs to be a way to point the algorithm to this folder nice and easily.
