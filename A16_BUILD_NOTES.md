# VCamera A16 Next — stability baseline

This branch intentionally focuses on Android 16 container stability before any virtual-camera integration.

Changes from upstream Blacks-BlackBox:
- device spoofing is disabled in the guest application lifecycle;
- GPS rocker initialization is disabled;
- hide-root behavior is forced off;
- VPN routing is forced off in the guest configuration;
- existing Android 16 runtime/service/IME fixes from Blacks-BlackBox are retained;
- no Snapchat-specific integrity or environment-detection bypass is included;
- VCamera media/camera replacement is not integrated yet.

## Acceptance test
1. Install the universal or arm64 debug APK.
2. Clone/import a benign app such as Telegram.
3. Launch it at least three times across exit/re-entry.
4. Verify keyboard input.
5. Verify networking and ordinary Android intents.
6. Verify the real camera path before any virtual-camera work begins.

Only after this baseline is stable should the VCamera media decoder/camera layer be integrated.
