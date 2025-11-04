# Transcoded

A Handbrake queue server for encoding digital media libraries.

I have recently begun a physical media collection, and have digitised my library to use with the excellent [Jellyfin](https://jellyfin.org/) media system.

However, due to the incredibly high quality of most Blu-ray media, playing from those files directly over the internet is not sensible. As such, I created Transcoded, a queue system for Handbrake which helps to track and automate the process of converting my media library into streaming-friendly encodings.

The software features:

* Automatic library scanning, with detection of main features.
* Automatic determination of Handbrake presets, to allow users to track the progress of encoding their library.
* A queue system to allow users to add encoding jobs to a queue.
* Options for limiting Handbrake's CPU usage, reducing the load on my home server.

By developing this software, I was able to optimise my process for transcoding my media library, and ensure that all of my media was correctly detected and organised within Jellyfin.