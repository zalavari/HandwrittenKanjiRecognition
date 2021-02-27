# Handwritten Kanji Recognition

## About

This project is created for the AIT Deep Learning course in 2021 Spring.
The goal is present the studied techniques through a deep learning application.

The task is to recognize handwritten Kanji and interpret them as digital UTF-8 characters.

Author:
Márton Zalavári

## Motivation
I choose this project, because recognizing different characters is a very important field of research, while it is still a relatively simple.

Digit recognizing is one of the most basic topics when getting acquainted both with computer vision and deep learning. I choose to do it with a twist, and instead of digits I try to recognize somewhat more exotic characters, namely the Japanese Kanjis.

In truth it's became a challenge between AI experts to recognize cursive-style writing, which is much harder to read, even for a human being. There is an already prepared dataset available solely for this purpose. I did not want to raise the bar too high, so for the time being I deal with only the more readable format. (Also it's not fun to use an already prepared dataset.) [1]

The topic is also important, if one want to identify a kanji, but does not know the exact stroke-order. The biggest commercially available handwriting recognition methods (google translate etc.) usually assumes that the user knows the exact stroke-order and predict very poorly otherwise.

## The Data
I use the ETL Character Database which contains numerous handwritten characters, so it is good for starting. It is free to download for research purposes. [2]

For the time being I only used the ETL8G dataset, which contains the 881 most commonly used Kanji (and 75 additional Hiragana) written by 160 different people. Each image consists of 128(X-axis size) * 127(Y-axis size) pixels, and each pixel is encoded on 4bit (16 gray level) [3]

Also I want to highlight, that my solution heavily depends on some other solutions (linked at the references), but even if some code is similar, I did more research, changed, fixed and simplified plenty of things. [4]

## Plans for the semester
### Milestone 1
Reading and pre-processing the data.

I read the datasets and load them into python code. I filter out the 75 hiragana character and use only the Kanjis.
After reshaping the arrays, I make appropriate labels for each image.
Also, I downscale the images, so our network has to deal with smaller inputs.

Some example is shown below. We have the actual Kanji, a corresponding image extracted from the database, and the same image downscaled.

![chrome_2102271632_z73b3kcUyb](https://user-images.githubusercontent.com/43651931/109393428-d76c1b00-7921-11eb-864f-caa462e2a30e.png)

### Milestone 2
Creating and training a neural network.

### Milestone 3
Fine tuning the solution, adding the option to draw a Kanji on a canvas, and recognize it in real-time.

Maybe use more datasets and add more different characters.
If the model performs well, we could extend the solution to recognize Kana as well.


## References

1. Tarin Clanuwat, Mikel Bober-Irizar, Asanobu Kitamoto, Alex Lamb, Kazuaki Yamamoto, David Ha, "Deep Learning for Classical Japanese Literature", arXiv:1812.01718. 
   KMNIST Dataset" (created by CODH), adapted from "Kuzushiji Dataset" (created by NIJL and others), doi:10.20676/00000341
2. Electrotechnical Laboratory, Japanese Technical Committee for Optical Character Recognition, ETL Character Database, 1973-1984.
3. http://etlcdb.db.aist.go.jp/etlcdb/etln/form_e8g.htm
4. https://github.com/Nippon2019/Handwritten-Japanese-Recognition
