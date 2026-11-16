# GoTomHackingClient

Fresh repository foundation for a Minecraft 1.21.5 Fabric client.

## Build
The GitHub Actions workflow builds with Java 21 and Gradle. Open **Actions**, select the newest successful run, and download the `gotomhackingclient-build` artifact. Use the normal JAR, not the `-sources.jar`.

## Current baseline
This project includes the ClickGUI, module framework, config persistence, and the existing basic utility/HUD modules. The ClickGUI overrides `Screen.applyBlur()` with an empty implementation so Minecraft's screen blur post-process cannot soften the custom-drawn foreground. It keeps the existing dim overlay and panel design. This source change has not yet been compiled or tested in-game in this environment.

A successful CI build proves compilation, not in-game correctness. Test in a disposable singleplayer world first.

## Development roadmap
Features will be implemented in small, tested batches. Each module must have real behaviour, settings where needed, safe enable/disable cleanup, and an in-game test. A name in a GUI is not considered an implementation.

Automation and combat testing are restricted to singleplayer or explicitly authorized private test environments. This project will not implement client-crashing attacks, anti-cheat evasion, stealth, or public-server exploitation.
