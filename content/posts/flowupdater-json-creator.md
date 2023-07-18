+++
title = "Coding jurney: rewriting Flowupdater Json Creator in Rust"
date = "2023-07-18T00:32:40+02:00"
author = "Zuygui"
authorTwitter = "" #do not include @
cover = ""
tags = ["rust", "minecraft", "flowupdater", "cli"]
keywords = ["flowudpater", "minecraft", "cli"]
description = "How I wrote a CLI tool to make JSON writing for flowupdater faster."
showFullContent = false
readingTime = true
hideComments = false
color = "" #color from the theme settings
+++

# Table of Contents

- [Introduction](#introduction)
- [Flow Updater](#flow-updater)
- [Tech Stack](#tech-stack)
- [The goal](#the-goal)
- [Development Steps](#development-steps)
- [What's Next?](#whats-next)
- [Credits](#credits)
- [Conclusion](#conclusion)

# Introduction

While discussing and assisting people on the [Support Launcher](https://discord.gg/zJkc7nZHRk) Discord server, a discord server for helping people to make customs Minecraft launchers, I realized that creating JSON files compatible with [Flow Updater](https://github.com/FlowArg/FlowUpdater) was time-consuming and tedious. This led me to the idea of developing a command-line tool to replace [the existing desktop application](https://github.com/FlowArg/FlowUpdaterJsonCreator).

# Flow Updater

Flow updater is a Java library to install, update and launch Minecraft (retrieved from officials servers) and mods loaded through Forge or any other mods loader. To load the mod list and other configurations, it is possible to host a JSON file and pass it into the library, ... So a JSON compatible with FlowUpdater looks like :

_Note:_ JSON (JavaScript Object Notation) is a data file format easy to read and write for humans and machines.

```json
{
  "curseFiles": [
    {
      "projectID": 123456, // random curseforge project id
      "fileID": 123456 // random curseforge file id
    }
  ]
}
```

Writing this JSON is very tedious and time-consuming because you have to find the project id and the file id for each mod. So I decided to write a CLI tool to make this task easier.

# Tech Stack

To build this software, I had to utilize several tools, including:

- [Rust](https://rust-lang.com), a compiled functional programming language developed by Mozilla (the company behind Firefox).
- [Request TTY](https://github.com/Lutetium-Vanadium/requestty/), a Rust crate that facilitates the creation of command-line forms.
- [Eternal API](https://docs.curseforge.com/), the new Curseforge API, which allows me to retrieve the necessary information from mods for JSON generation.
- [Serde JSON](https://github.com/serde-rs/json), an extension of the `serde` crate that enables the serialization and deserialization of Rust structs.

I've only mentioned the most significant elements present in the [source code](https://github.com/zuygui/flowupdater-json-creator).

# The goal

I wanna replace the Java application (GUI) by a CLI application in Rust. I also wanna make the application more fast and accessible. Finally, I wanna add new features to the application like locals mods support and archives exports.

# Development Steps

I began by developing a wrapper for the CurseForge API, which turned out to be a lengthy and challenging process but constituted the bulk of the work. Next, I coded the CLI, which was relatively straightforward. Instead of using the [`clap`](https://github.com/clap-rs/clap) crate, a Rust tool for generating CLIs, I opted for the following line of code:

```rs
fn main() {
       let args: Vec<String> = std::env::args().collect();
}
```

This code snippet captures the input to the program: the `main` function defines an immutable variable called `args`, which is a vector (a list with indefinite length, for the sake of simplicity here) of type `String`. Thus, we obtain a list of all the arguments given when executing the binary file (including the application's name). I concluded the development of the first version with the JSON file generation.

# What's Next?

Due to my heavy workload with my integration into the development team of the [WEB Aide Jeune](https://aidejeune.fr) association, I have less time to continue making progress on the project. This does not mean that I'm abandoning it; I'm simply moving forward at a slower pace. I sincerely thank [Bricklou](https://github.com/Bricklou) for helping me maintain the project. We are actively working on creating new features.

# Credits

I wanna thank [Bricklou](https://github.com/bricklou) for maintening the project with me. I also wanna thank [FlowArg](https://github.com/FlowArg) for creating the original project. Finally, I wanna thank [Asthowen](https://github.com/Asthowen) for helping me with Github CI.

# Conclusion

Thank you for reading this article on my blog. I hope you enjoyed it. Please feel free to leave a comment and give the GitHub repository of this blog a star ⭐.
