<div align="center">

# AnyTogether

**Play the PS5 games you own on your Mac, your PC and your phone, with your friends.**
Open source, made by players.

[Website](https://anytogether.net) · [Full specs](https://anytogether.net/specs) · [Download](https://github.com/AnyTogether/AnyPS5-ARM/releases/latest) · [Roadmap](https://anytogether.net/roadmap)

</div>

---

### What's here

| Project | What it is | Platforms |
|---|---|---|
| **[AnyPS5-ARM](https://github.com/AnyTogether/AnyPS5-ARM)** | The ARM core: the PS5 engine port for Apple silicon, plus the Windows and Linux engine builds. Every release, with all platforms, is published here | macOS · Windows · Linux |
| **[AnyLauncher](https://github.com/AnyTogether/AnyLauncher)** | The console-style launcher for the Mac, written in SwiftUI | macOS |
| **[AnyLauncher Port](https://github.com/AnyTogether/AnyLauncher-Port)** | The same launcher for Windows and Linux, written in Flutter, with Steam and Steam Deck support | Windows · Linux |
| **[AnyMobile](https://github.com/AnyTogether/AnyMobile)** | The phone app: your phone as a DualSense, plus friends, party, voice and messages | iOS · Android |
| **[AnyTogether](https://github.com/AnyTogether/AnyTogether)** | Co-op and online: accounts, friends, parties and voice, messages, trophies, Play Together, Captures, cloud saves. You can run your own server | Web · self-hosted |
| **[Website](https://anytogether.net)** | Downloads, full specs, roadmap and your account in the browser. Its code is `apps/web` in the AnyTogether repo | Web |

### Highlights

- 🎮 **Couch-ready launcher**: pad-first navigation, PS quick menu, profiles, controller management (DualSense, DualShock 4/3, Xbox, Switch Pro and more)
- 🌐 **Online play**: a virtual LAN between players over WebRTC, Play Together from a party, Windows, Linux and Mac in the same game
- 📱 **Phone as a controller**: the app, or no app at all, by scanning a QR code in the browser
- 📸 **Captures**: clips and screenshots from the Create button, shared with friends, with likes and comments
- 🔏 **Signed releases**: every file is checked before the launcher installs it

### Get started

1. Download the latest release for your platform: [Mac, phone, Windows and Linux](https://github.com/AnyTogether/AnyPS5-ARM/releases/latest).
2. Add your own decrypted game dumps.
3. Sign in to AnyTogether to play with friends, or stay offline.

### Credits

**The core**

- **[AnyPS5](https://github.com/boykopovar/AnyPS5) by boykopovar** is where the core comes from: the relinker that turns a PS5 executable into a native program and the reimplemented system libraries. AnyPS5-ARM is its port to Apple silicon Macs, and every engine feature here starts from that work.
- **[mugurc's community macOS port](https://github.com/mugurc/AnyPS5/tree/macos-port)** of AnyPS5 is the port AnyPS5-ARM builds on.
- **[MoltenVK](https://github.com/KhronosGroup/MoltenVK)** (Khronos, Apache-2.0) runs the PS5 graphics driver's Vulkan on Metal, and **[SDL](https://github.com/libsdl-org/SDL)** (zlib) reads the controllers in games and in AnyLauncher Port.

**Online play**

- **The online design comes from [AnyPlay](https://github.com/anyplaynet).** Our bridge between the engine and the launcher follows AnyPlay's bridge spec ([anyplaynet/network](https://github.com/anyplaynet/network/blob/main/spec/bridge-protocol.md), MIT/Apache-2.0): the frame header, the message numbering, the virtual LAN range and the A/B/C screening of games come from it. Stream P2P sockets over the bridge follow the approach of AnyPlay's engine bridge ([anyplaynet/AnyPS5](https://github.com/anyplaynet/AnyPS5), GPL-2.0).
- **Ideas AnyPlay shipped first** ([anyplaynet/launcher](https://github.com/anyplaynet/launcher), [anyplaynet/cloud](https://github.com/anyplaynet/cloud)): "Try anyway" on a Play Together version mismatch, retiring old launchers with "Update required", asking before leave party / remove friend and similar actions, the noise suppression switch, the public profile switch and the compatibility filters.
- **A phone browser as a controller via a QR code** comes from [LudusCtrl](https://github.com/parl0v/ludusctrl)'s browser client by Josip Parlov (@parl0v), shipped in AnyPlay.

Our code is written independently; where we followed someone's design or idea, it is named here.

