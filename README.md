# Nairobi GenUI Restaurant Finder

This version is rewritten against the current `genui` package API documented on pub.dev and Flutter docs.

## Current API used
- `genui: ^0.9.2`
- `SurfaceController(catalogs: [CoreCatalogItems.asCatalog()])`
- `A2uiTransportAdapter(onSend: ...)`
- `Conversation(controller: ..., transport: ...)`
- `Surface(host: _conversation.host, surfaceId: id)`
- `ChatMessage.user(text)`

## How it works
This app uses a local mock A2UI sender instead of a real remote model. When the user enters a restaurant query, the app builds A2UI messages in JSON text, streams them into `A2uiTransportAdapter.addChunk()`, and lets GenUI render the resulting surfaces.

That means it uses the real current GenUI runtime API, but still requires no API key.

## Run
```bash
flutter pub get
flutter run
```

## Example queries
- `Ethiopian`
- `Westlands`
- `Coffee in CBD`
- `Pizza`