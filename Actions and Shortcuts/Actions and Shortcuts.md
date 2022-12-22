# Shortcuts

### Simple tab examplet

    child: Shortcuts(
        shortcuts: const <ShortcutActivator, Intent>{
        // Pressing space in the field will now move to the next field.
        SingleActivator(LogicalKeyboardKey.tab): NextFocusIntent(),
    },
        child: FocusTraversalGroup(
