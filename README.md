# Lateral

A minimalist cross-platform application inspired by Brian Eno's Oblique Strategies, designed to help artists, writers, musicians, and creators overcome creative blocks through lateral thinking prompts.

<p align="center">
  <img src="/api/placeholder/300/150" alt="Lateral App" />
</p>

## About

Lateral delivers random, thought-provoking prompts to encourage unconventional thinking and help break creative stagnation. With a deliberately minimalist interface, the app feels like drawing a card from a digital deck—providing just enough disruption to your creative process to spark new directions.

## Key Features

- **Dynamic Prompt Generator**: Tap to receive a random creative strategy
- **Minimalist Interface**: No explanations or clutter—just the prompt
- **Cross-Platform**: Available on both Android and iOS
- **Offline Support**: No internet connection required

## Technology

Lateral is built using Kotlin Multiplatform (KMP), allowing for shared business logic while maintaining native UI experiences:

- **Shared Code**: Kotlin Multiplatform
- **Android UI**: Jetpack Compose
- **iOS UI**: SwiftUI
- **Architecture**: MVVM with unidirectional data flow

## Getting Started

### Prerequisites

- Android Studio Arctic Fox or newer
- Xcode 13 or newer (for iOS development)
- JDK 11 or newer
- Kotlin Multiplatform Mobile plugin for Android Studio

### Building the Project

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/creative-spark.git
   ```

2. Open the project in Android Studio

#### For Android:

- Select the androidApp configuration
- Run on your device or emulator

#### For iOS:

- Open the iosApp.xcworkspace in Xcode
- Select your target device
- Build and run

## Project Structure

```
creative-spark/
├── shared/          # Shared KMP code
│   ├── commonMain/  # Common code for all platforms
│   ├── androidMain/ # Android-specific code
│   └── iosMain/     # iOS-specific code
├── androidApp/      # Android application
└── iosApp/         # iOS application
```

## Development

### Adding New Prompts

Prompts are stored in `PromptRepository.kt` in the shared module. To add new prompts:

1. Open `shared/commonMain/repositories/PromptRepository.kt`
2. Add new entries to the prompts list

### Running Tests

```bash
./gradlew :shared:allTests     # Run all tests
./gradlew :shared:jvmTest      # Run JVM tests
./gradlew :androidApp:testDebug # Run Android tests
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Design Principles

- **Less is more**: Minimal interface with focused functionality
- **Mystery over instruction**: Prompts are open to interpretation
- **Calm aesthetics**: Dark mode, serif fonts, muted colors

## License

This project is licensed under the MIT License - see the LICENSE file for details.
