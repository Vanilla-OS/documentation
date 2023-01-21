# How to translate Vanilla OS - Documentation. Guide

## Introduction

This guide will help you to translate Vanilla OS into your language. Vanilla OS is a free and open source operating system. If you want to contribute to our project and translate it to your language, you can do it. This guide will help you to do it.

## How to translate Vanilla OS

### 1. Fork the repository

First of all, you need to fork the repository. You can do it by clicking the "Fork" button on the top right corner of the repository page. After that, you will have a copy of the repository in your account. You can edit it and translate it.

### 2. Clone the repository

After you forked the repository, you need to clone it to your computer. You can do it by clicking the "Code" button and copying the link. Then, open your terminal and type the following command:

```bash
git clone [your link]
```

### 3. Translate the files

To translate the Markdown files, you need to create the localization folder inside `./i18n/` folder. Then, you need to copy all the files from English version. On Linux, you can run the commands below:
```bash
mkdir -p i18n/[language]/docusaurus-plugin-content-docs/current
cp -r docs/** i18n/[language]/docusaurus-plugin-content-docs/current
```
Where `[language]` is the language code of your language. For example, if you want to translate it to Turkish, you need to use `tr` as the language code. After that, you need to translate the files. You can use any text editor to do it. You can also use an online Markdown editor like [StackEdit](https://stackedit.io/app).

### 4. Commit and push the changes

After you translated the files, you need to commit and push the changes. You can do it by running the commands below:
```bash
git add .
git commit -m "Translated to [language]"
git push
```
Where `[language]` is the language name of your language. For example, if you translated it to Turkish, you need to use `Turkish` as the language name. After that, you need to create a pull request.

### 5. Create a pull request

After you pushed the changes, you need to create a pull request. You can do it by clicking the "Pull requests" button on the top of the repository page. Then, you need to click the "New pull request" button. After that, you need to click the "Compare across forks" button. Then, you need to select your fork as the "head repository" and the main repository as the "base repository". After that, you need to click the "Create pull request" button. Then, you need to write a title and a description for your pull request. After that, you need to click the "Create pull request" button. After that, you need to wait for the pull request to be merged.
