---
title: অপরিবর্তনীয়তা (এবিরুট) - ভ্যানিলা ওএস
description: কীভাবে এবিরুট ব্যবহার করতে হয় তা শিখুন।
---

# অপরিবর্তনীয়তা (`abroot`)

`abroot` এমন একটি ইউটিলিটি যা ২ টি (A⟺B) রুট বিভাজনের মাঝে অদলবদল ঘটানোর মাধ্যমে অপরিবর্তনীয়তা ও পারমাণবিকতা প্রদান করে। এছাড়াও এটি একটি অদলবদলকরণ শেলের মাধ্যমে চাহিদা-মাফিক অদলবদলের সুযোগ প্রদান করে।

## যেভাবে এটি কাজ করে

লিনাক্স ফাইল ব্যবস্থাপনা মূলত একটি ক্রমোচ্চ শ্রেণিবিভাগমূলক ফাইল ব্যবস্থাপনা যা রুট ও অন্যান্য ডিরেক্টরিগুলি ধারণ করে।
রুট হচ্ছে প্রধান ক্রমোচ্চ শ্রেণিবিভাগমূলক ডিরেক্টরি যা অন্যান্য সকল ডিরেক্টরিকে ধারণ করে।
অপরিবর্তনীয় ফাইল ব্যবস্থাপনাগুলিতে রুট বিভাজনটি রিড-ওনলি থাকে, যা গুরুত্বপূর্ণ প্যাকেজসমূহ, যেমন ড্রাইভার ইত্যাদিকে হোস্টে ইনস্টল করতে বাঁধা দেয়।

`abroot` আপনাকে ফাইল ব্যবস্থাপনার অপরিবর্তনীয়তা বজায় রেখেই কার্নেল মড্যুলসমূহ, ড্রাইভারসমূহ ও অন্যান্য গুরুত্বপূর্ণ প্যাকেজগুলি ইন্সটল করার সুযোগ প্রদান করে।

যখন `abroot`-এ কোনো কমান্ড রান করা হয়, তখন দ্বিতীয় রুট বিভাজনে একটি অদলবদলকরণ শেলের মাধ্যমে একটি অদলবদল প্রক্রিয়া শুরু হয়। যদি অদলবদল প্রক্রিয়াটি সফল হয়, তাহলে একটি প্রলেপ ব্যবহারের মাধ্যমে পরিবর্তনগুলি প্রয়োগ করা হয় এবং একটি রিবুটের মাধ্যমে বর্তমানে সচল বুট বিভাজনে পরিবর্তনগুলি সমন্বয়সাধন করা হয়। আর যদি অদলবদল প্রক্রিয়াটি ব্যর্থ হয়, তাহলে কোনো পরিবর্তনই প্রয়োগ করা হয় না (পারমাণবিকতা নামক একটি বৈশিষ্ট্য উপলদ্ধ থাকার দরুন)। এছাড়াও `abroot` আপনাকে `abroot shell` কমান্ড ব্যবহারের মাধ্যমে চাহিদা-মাফিক অদলবদলের সুযোগ দেয়।

`abroot` এর জন্য আবশ্যক হওয়ায় ভ্যানিলা ওএস ইনস্টলেশনের সময় উভয় অবস্থার জন্য স্বতন্ত্র রুট ও বুট বিভাজন তৈরি করে (প্রতি রুট বিভাজনে 20GB করে)।

## অবস্থাবলি

`abroot` এর দুইটি অবস্থা রয়েছে - বর্তমান ও ভবিষ্যৎ। যখন আপনি প্রথমবারের মতো আপনার ভ্যানিলা ওএস ইনস্টলেশনে অবস্থান করেন, তখন বর্তমান অবস্থাটি থাকে A। আর যখন আপনি সিস্টেম রিবুট করেন, তখন অবস্থাটি স্বয়ংক্রিয়ভাবে B-তে পরিবর্তিত হয়ে যায়। যখন আপনি `abroot` ব্যবহার করে কোনো প্যাকেজ ইন্সটল করেন, তখন এটি ভবিষ্যৎ রুট বিভাজনে ইনস্টল হয় এবং একটি রিবুটের পর বর্তমান রুট বিভাজনের সাথে সমন্বয় সাধিত হয়।  

## আপডেটসমূহ

এবিরুট `vso` নামক একটি ইউটিলিটিকে ক্ষমতায়ন করে যা স্মার্ট স্বয়ংক্রিয় আপডেট এবং আড়ালে থেকে ভবিষ্যৎ রুট বিভাজনে আপডেটগুলি ইনস্টল করার সুযোগ দেয়। এটি সময় বাঁচায় কারণ এতে রিবুটের সময় অফলাইন আপডেটের প্রয়োজন হয় না।

## কার্নেল প্যারামিটারসমূহ 

`abroot` allows setting custom kernel parameters in case a driver or custom setup requires it. By default, `abroot` reads the contents of `/etc/default/abroot_kargs`, which must **not** be edited. Instead, you should use the provided command to manage your parameters:

```
sudo abroot kargs edit
```

The command above will open the parameters file in your default command-line text editor (`nano` by default), but you can override it by using the `$EDITOR` environment variable before the command. So, for example, if you want to edit the arguments using `vim`, you can run `sudo EDITOR=vim abroot kargs edit`.

[Kernel parameters](https://www.kernel.org/doc/html/v4.14/admin-guide/kernel-parameters.html) must be separated by spaces and should **not** have line breaks between them. Furthermore, you should not remove the default parameters unless you know what you're doing, as changing them could make your system unbootable.

**NOTE**: The kernel parameters are applied only to your future root, so you can always enter the previous root in case something goes wrong.

## নামকরণ

এবিরুট নামটি দুইটি এ ও বি (A⟺B) রুট বিভাজনের মাঝে অদলবদল প্রক্রিয়ার দিকে ইঙ্গিত করে।

## ব্যবহার

- [ম্যানপেজ সহায়িকা](/docs/ABRoot/manpage)
- [আপনার ডিস্ট্রিবিউশনে পোর্ট করুন](/docs/ABRoot/porting)
