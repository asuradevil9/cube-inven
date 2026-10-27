Cube Empty - Shared Stash 100-tab source update

Behavior:
- Middle-click the Horadric Cube while hovering it.
- Each cube item is attempted on shared-stash tabs 1 through 100 (SDK page indexes 0..99).
- Each tab uses automatic placement. If a tab is full or inactive/unavailable, the next tab is tried.
- If no tab accepts the item, it stays in the cube.
- SharedStashWrite capability is checked before activation.

Important:
- The 100-tab search limit means tabs 1-100 are checked; it does not enable/create 100 tabs. Configure the active D2RLoader/mod shared stash to expose those tabs.
- This is modified source only. The source archive supplied by the user contains plugin.cpp and plugin.rc but not the SDK headers or build configuration, so a compiled DLL and in-game verification are not included.
- Rebuild against the matching D2RLoader Plugin SDK. Test with a backup of the character/shared stash first.
