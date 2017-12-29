---
layout: post
title: "Extract random images from videos in Python"
categories: [Python]
comments: true
vertical: Code
---

I am working on the automatic logo detection in the sports videos using Deep Learning. For this, i will
be using the Faster-RCNN model.

To train the model with the annotations in the images, I required random images from the selected videos.
Following is the script (this is in python2; for python3, it should just be a matter of using parentheses with print) that I used for extracting images from videos.

```python

import skvideo.io
from matplotlib import pyplot as plt
import random

# Return 'num_images' no. of random images
def random_items(iterator, num_images=1):
    selected_items = [None] * num_images

    for item_index, item in enumerate(iterator):
        for selected_item_index in xrange(num_images):
            if not random.randint(0, item_index):
                selected_items[selected_item_index] = item

    return selected_items

# Read the video, extract images and save them to a directory
def extract_images(video_path, num_images, save_to_path):
    # Use vreader as it loads the video frame-by-frame
    # If it is a large video, using vread() may exhaust the memory
    videogen = skvideo.io.vreader(video_path)
    random_set = random_items(videogen, num_images)

    count = 0

    for frame in random_set:
        directory = "{0}/image{1}.png".format(save_to_path, count)
        plt.imsave(directory, frame)
        # if you instead want to just show the images in a notebook
        # instead of saving, use imshow()
        # plt.imshow(frame, interpolation='nearest')
        plt.show()
        count += 1

if __name__ == '__main__':

    import argparse

    parser = argparse.ArgumentParser()
    parser.add_argument('--video-path', required=True)
    parser.add_argument('--num-images', required=True)
    parser.add_argument('--save-to-path', required=True)
    args = parser.parse_args()

    extract_images(args.video_path, int(args.num_images), args.save_to_path)

```

Run the above code using the following command (I wanted 250 random images from this video):

```
python extract_images_from_videos.py --video-path="/home/alisha/AFL 2017 Season Highlights-0O3rHhzO9VQ.mkv" --num-images=250 --save-to-path="/home/alisha/test_folder"

```

I hope this helps! :)