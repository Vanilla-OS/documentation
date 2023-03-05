---
title: প্যাকেজ ম্যানেজার (apx) - ভ্যানিলা ওএস
description: কীভাবে ভ্যনিলা ওএস প্যাকেজ ম্যানেজার apx ব্যবহার করতে হয় তা জানুন।
---

# প্যাকেজ ম্যানেজার (`apx`)

`apx` হচ্ছে ভ্যানিলা ওএস প্যাকেজ ম্যানেজার যা ব্যবহার করা সহজ এবং এটি রুট ফাইল ব্যবস্থাপনায় কোনো পরিবর্তন ব্যতিতই কন্টেইনারের ভিতরে বিভিন্ন উৎস থেকে প্যাবেজ ইন্সটল করা সমর্থন করে।

## যেভাবে এটি কাজ করে

`apx` প্যাকেজ ম্যানেজমেন্টের অভিনব এক পন্থা উপস্থাপন করেছে। বুদ্ধিটা হচ্ছে, আপনার সিস্টেমকে শুধুমাত্র
আপনার ফাইলপত্র জমা রাখার একটা বাক্স হিসেবে ব্যবহার করবেন। যা এটাকে বিভিন্ন প্যাকেজ থেকে মুক্ত রাখবে
আর এটাকে অসম্পূর্ণ, পারিপাট্যহীন ভাবে তৈরি অথবা সংঘাতময় প্যাকেজের কারণে নষ্ট হয়ে যাওয়ার ঝুঁকি কমিয়ে দিবে।

এটি সম্ভব হয় 'apx' কর্তৃক নিয়ন্ত্রিত এক বা একাধিক কন্টেইনারের মধ্যে সফটওয়্যার ইনস্টল করার মাধ্যমে। আপনার সিস্টেম রিসোর্সের প্রতি এর এক্সেস সীমাবদ্ধ থাকে। তবুও এটি সিস্টেমে থাকা একই ড্রাইভার, ডিস্প্লে সার্ভার ইত্যাদি ব্যবহার করতে পারে।

আপনার হোম ডিরেক্টরি কনটেইনারের ভিতরেও ম্যাপ করা থাকে। তাই আপনি হোমে থাকা সকল কনফিগ ফাইল,
সেটিংস, অন্যান্য প্রয়োজনীয় ড্যাটা কন্টেইনারে ভিতর ইনস্টল করা প্যাকেজেও এক্সেস করতে পারবেন। একইভাবে সকল
ফাইল কন্টেইনারে থাকা সফটওয়্যারে এক্সেস করতে পারবেন। (যেমন হোমে থাকা কোনো ডকুমেন্ট ফাইল কন্টেইনারে থাকা লিব্রাঅফিসে ওপেন করতে পারবেন।)

### হোস্ট সিস্টেম

While installing software on the host is against the project's ideology, there are cases where it is essential. For example, when you need to 
install a kernel module or driver.

যদিও হোস্ট সিস্টেমে সফটওয়্যার ইনস্টল করাটা এই প্রকল্পের আদর্শের সাথে সাংঘর্ষিক, তবু কখনো কখনো এটি জরুরিও হতে পারে। উদাহরণস্বরূপ, যখন আপনার কোনো কার্নেল মড্যুল বা ড্রাইভার
ইন্সটল করার দরকার হয়।

এসব ক্ষেত্রে আপনি কন্টেইনারকে পাশ কাটিয়ে সরাসরি হোস্টে ইনস্টল করতে চাইলে `abroot exec apt install <package_name>` অথবা `abroot shell apt install <package_name>` ব্যবহার করতে পারেন।
কিন্তু সতর্ক থাকবেন, এই পন্থাটি প্রণিধানযোগ্য নয়।

### বিভিন্ন উৎস

By default, `apx` provides a container based on your Linux distribution (Ubuntu 
22.10 for Vanilla OS 22.10) and wraps all commands from the distribution's 
package manager (`apt` for Ubuntu).

Nevertheless, you can install packages from package other distributions. For example, using the `--aur` flag, a new
container based on Arch Linux will be created. Here, `apx` will manage the packages 
from the AUR (Pacman and yay), tightly integrating them with the host system. Using the `--dnf` flag with `apx` will create a new container based on Fedora Linux. Here, `apx` will manage packages from Fedora's DNF repository,  tightly integrating them with the host system. 

For GUI packages created inside `apx` containers,`.desktop` files are created automatically and added to the Applications menu. These applications are displayed beside other applications in the "Open with" menu in nautilus. GUI Packages installed inside containers gets shown in the Sub System section in the [Vanilla control center](/docs/vanilla-control-center).

For quality control, we are limiting this feature to specific implementations. Currently, only `--aur` and `--dnf` flags are supported, but 
we are planning to implement support for the Nix package manager as well in future.

### নামকরণ

The name `apx` comes from **apt (Advanced Packaging Tool)**, the package manager used by Debian and its derivatives. **X** consists of two lines (host and container) overlapping each other, where the container is on top, meaning 
it is on top of the host system.

## ব্যবহার

- [Manpage](/docs/apx/manpage)
