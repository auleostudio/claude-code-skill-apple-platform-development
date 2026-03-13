---
name: design
description: Design system skills for modern Apple platform UI including Liquid Glass, animations, and visual design patterns. Use when implementing new design language features.
allowed-tools: [Read, Write, Edit, Glob, Grep, AskUserQuestion]
---

# Design Skills

Skills for implementing Apple's modern design systems across platforms.

## When This Skill Activates

Use this skill when the user:
- Asks about Liquid Glass design
- Wants to implement modern Apple UI effects
- Needs guidance on visual design patterns
- Asks about materials, transparency, or blur effects
- Wants to create fluid animations
- Asks about **spring**, **bounce**, or **snappy** animations
- Wants **PhaseAnimator** or **KeyframeAnimator** help
- Needs **view transitions**, **matched geometry**, or **hero transitions**
- Wants **SF Symbol effects** (bounce, pulse, wiggle, breathe)
- Asks about **animation completions** or **withAnimation**
- Needs **Apple Design Resources** (UI kits, templates, fonts, bezels)
- Asks about **SF Symbols**, **SF Pro**, or system fonts
- Needs **app icon templates** or **production templates**
- Wants **product bezels** for marketing screenshots
- Asks about **Icon Composer** for layered icons

## Available Skills

### liquid-glass/
Comprehensive Liquid Glass implementation for iOS 26+, macOS 26+.
- SwiftUI `.glassEffect()` API
- AppKit `NSGlassEffectView`
- GlassEffectContainer patterns
- Morphing transitions
- Interactive effects
- Button styles

### animation-patterns/
SwiftUI animation patterns for iOS 13–18+.
- Spring configurations (3 API generations)
- PhaseAnimator and KeyframeAnimator (iOS 17+)
- View transitions, matched geometry, navigation transitions
- SF Symbol effects
- Animation completions, transactions, timing curves

### apple-design-resource/
Official Apple Design Resources reference for all platforms.
- UI Kits (Figma, Sketch) for iOS, macOS, watchOS, visionOS, tvOS
- App icon templates and production templates
- System fonts (SF Pro, SF Compact, SF Mono, New York)
- SF Symbols 7 (6,900+ symbols)
- Icon Composer for layered Liquid Glass icons
- Technology-specific templates (Apple Pay, Sign in with Apple, etc.)
- Product bezels for marketing materials
- Parallax tools for tvOS/visionOS

## Key Principles

### 1. Platform Consistency
- Follow Apple Human Interface Guidelines
- Use system-provided APIs
- Respect user appearance preferences

### 2. Performance
- Use GlassEffectContainer for multiple effects
- Limit number of glass effects per view
- Consider GPU resources

### 3. Visual Hierarchy
- Glass effects create depth and layering
- Use tints to indicate prominence
- Combine with appropriate shadows

## Reference Documentation

- [Implementing Liquid Glass in SwiftUI](https://developer.apple.com/documentation/swiftui/implementing-liquid-glass-design)
- [Implementing Liquid Glass in AppKit](https://developer.apple.com/documentation/appkit/implementing-liquid-glass-design)
