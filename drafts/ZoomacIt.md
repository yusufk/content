<!--
title: ZoomacIt - ZoomIt for Mac
date: 2026-05-24
-->

# ZoomacIt - Bringing ZoomIt to the Mac

During my time at Microsoft, I watched presenters wield ZoomIt like a superpower. Scott Hanselman in particular - the way he'd zoom into code, draw arrows, highlight sections mid-demo - it was seamless. The audience never lost focus because he could direct their attention precisely where it needed to be.

When I moved back to Mac full-time, I missed it immediately. There's nothing native on macOS that comes close. ⌘+ zooms the whole screen accessibility-style, but there's no freeze-and-annotate, no live zoom, no quick snip workflow.

Then I heard Scott and Mark on their podcast talking about modifying ZoomIt using vibe coding - AI-assisted development to add features. That was the spark. If they could extend it with AI, I could port it to Mac with AI. I found [ZoomacIt](https://github.com/07JP27/ZoomacIt), an existing open-source effort that had the foundation (Still Zoom, Draw, Break Timer) but was missing the features I used most.

## What I contributed

Over a weekend session with my AI assistant, I implemented:

- **Live Zoom** (⌃⇧1) - real-time screen magnification using ScreenCaptureKit's SCStream at 60fps. Videos keep playing, terminals keep scrolling. Zero-copy rendering via IOSurface.
- **DemoType** (⌃⇧D) - paste your demo commands into a dialog, and it types them character-by-character into whatever app had focus. Perfect for live coding demos where you don't want typos.
- **Snip** (⌃4 / ⌃⇧4) - region screenshot to clipboard or Desktop file, with a floating thumbnail preview you can click to reveal in Finder.
- **Draw cursors** - the pen cursor now reflects your active colour and size. Shape tools show contextual cursors: a rotating arrow/line during drag, a small square/circle that disappears as you draw the actual shape.
- **Focus restore** - all modes return focus to your previous app on dismiss, matching the Windows behaviour.

## The vibe coding experience

Every feature went from concept to working PR in under an hour. The AI handled the ScreenCaptureKit boilerplate, the Carbon hotkey registration, the AppKit cursor management - all the fiddly platform stuff that would normally take days of documentation diving. I focused on UX decisions and testing.

Four PRs submitted, all building on pure Swift 6 + AppKit with zero external dependencies.

## Links

- [GitHub](https://github.com/07JP27/ZoomacIt)
- [My PRs](https://github.com/07JP27/ZoomacIt/pulls?q=author%3Ayusufk)

#macos #swift #tools #opensource #vibecoding
