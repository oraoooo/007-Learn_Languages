# Learn Languages

Small scaffold projects for learning new language/framework ecosystems.

## learnDotNet/BlazorSample

A standard ASP.NET Core **Blazor Web App** template (`net10.0`) — Home, Counter, and Weather pages.

**Status: working.** Builds clean (0 warnings, 0 errors) and serves pages correctly.

```bash
cd learnDotNet/BlazorSample
dotnet run
# -> http://localhost:5200
```

## learnFlutter/namer_app

The official Flutter ["Namer App"](https://docs.flutter.dev/get-started/codelab) codelab — generates a random word pair, with a "Next" button and a favorites list to be added as the tutorial progresses.

**Status: builds and runs**, but mid-tutorial — two things to know:

- The **"Next" button doesn't update the word yet.** Its `onPressed` just does `print('button pressed!')`; it hasn't been wired up to generate a new `WordPair` and call `notifyListeners()`. That's expected at this point in the codelab, not a bug — the next step is adding a `getNext()` method to `MyAppState` and calling it from the button.
- `flutter test` **fails**, but the app itself isn't broken: `test/widget_test.dart` is still the default `flutter create` counter-app test (checks for text `'0'`/`'1'` and an `Icons.add` button), none of which exist in this app anymore. It should be rewritten to test the actual word-pair UI, or deleted until there's real app logic to test.

```bash
cd learnFlutter/namer_app
flutter pub get
flutter run        # launch on a connected device/simulator
flutter run -d macos  # or run as a native macOS app
```
