# Lateral

## Overview

Lateral is a minimalist cross-platform application inspired by Brian Eno's Oblique Strategies. The app serves as a digital deck of thought-provoking prompts designed to help artists, writers, musicians, and creators overcome creative blocks through lateral thinking.

## Technical Architecture

### Kotlin Multiplatform (KMP) Structure

The project leverages Kotlin Multiplatform to share business logic and data models while implementing native UI for each target platform.

```
- shared/
  - commonMain/
    - models/
    - repositories/
    - viewmodels/
  - androidMain/
  - iosMain/
- androidApp/
- iosApp/
```

### Core Components

#### Data Models

```kotlin
data class Prompt(
    val id: String,
    val text: String,
    val source: Source = Source.ORIGINAL
)

enum class Source {
    ORIGINAL,
    USER_CONTRIBUTED
}
```

#### Repositories

```kotlin
interface PromptRepository {
    fun getRandomPrompt(): Prompt
    suspend fun addUserPrompt(text: String): Prompt // For future implementation
}
```

#### ViewModels

```kotlin
class MainViewModel(private val promptRepository: PromptRepository) {
    val currentPrompt: StateFlow<Prompt?>
    fun drawNewPrompt()
}
```

### Platform-Specific UI Implementation

#### Android

- UI Framework: Jetpack Compose
- Theme: Dark mode with serif typography
- Animation: Card flip/draw animation
- Haptics: Subtle feedback on card draw

#### iOS

- UI Framework: SwiftUI
- Theme: Matching Android dark mode aesthetic
- Animation: Card flip/draw animation
- Haptics: Taptic Engine feedback on card draw

## Feature Specifications

### Phase 1: Core Functionality (MVP)

- Prompt Database: Initial set of 50 hand-curated creative prompts
- Random Draw: Single button interface for drawing a random prompt
- Minimalist UI: Clean, distraction-free interface with prompt displayed prominently

UI Flow:

1. App launch → Empty card/placeholder
2. "Draw a Card" button → Tap to reveal prompt
3. Prompt display → Clear, centered text with adequate whitespace
4. Return to step 2 for new prompt

### Phase 2: Enhanced Experience

- Animations: Smooth transitions between prompts
- Card History: Access to previously drawn cards
- Share Functionality: Export prompts as text or images
- Subtle Sounds: Optional audio feedback (toggle-able)

### Phase 3: Community & Expansion (Future)

- User Contributions: Submit new prompts to shared pool
- Themed Decks: Specialized prompt collections for different creative fields
- Creative Timer: Timed sessions paired with prompts
- Export Integration: Send prompts to other apps (Notion, Notes, etc.)

## Technical Requirements

### Core Technology

- Language: Kotlin 1.9+ for shared code
- UI: Platform-native (Compose for Android, SwiftUI for iOS)
- Build System: Gradle with KMP plugin

### Minimum Platform Versions

- Android: API 21 (Lollipop)
- iOS: iOS 14+

### Dependencies

- Coroutines: For asynchronous programming
- Kotlinx.serialization: For JSON parsing
- Multiplatform Settings: For preferences storage
- SQLDelight (Phase 3): For local database storage

### Non-Functional Requirements

- Performance: App launch under 1.5 seconds
- Size: APK/IPA under 15MB
- Offline Support: Full functionality without network connection
- Accessibility: Support for screen readers and dynamic text sizing

## Design Guidelines

### Visual Design

- Color Palette: Dark background (#121212) with muted accent colors
- Typography: Serif fonts for prompts, sans-serif for UI elements
- Spacing: Generous whitespace to maintain focus on the prompt
- Iconography: Minimal, only where absolutely necessary

### Interaction Design

- Animations: Subtle and purposeful, enhancing the card drawing experience
- Touch Targets: Minimum 44x44dp for all interactive elements
- Feedback: Visual and haptic confirmation for all actions
- Gestures: Swipe support for dismissing/cycling through prompts

## Testing Strategy

- Unit Tests: For repository and viewmodel logic
- UI Tests: For basic interaction flows
- Cross-Platform Testing: Verify consistent behavior across iOS and Android
- User Testing: Qualitative feedback from 5-10 creative professionals

## Deployment Strategy

- Android: Google Play Store
- iOS: Apple App Store
- Beta Testing: Internal testing followed by limited public beta

## Success Metrics

- Engagement: Average session time and frequency
- Retention: 7-day and 30-day return rate
- User Feedback: Qualitative feedback on prompt usefulness
- Creative Impact: Case studies of work created using the app prompts

# Project Specifications

## Overview

Lateral is a cross-platform mobile application that generates lateral thinking prompts to help users overcome creative blocks.

## Target Platforms

- iOS (iOS 14.0+)
- Android (API Level 24+)

## Core Features

### Prompt Generation

- Random selection from curated prompt database
- No repeat prompts until all have been shown
- Smooth animations for card transitions

### User Interface

- Dark mode by default
- Serif typography for prompts
- Gesture-based interactions
- Haptic feedback on prompt generation

### Data Management

- Local storage of prompts
- No internet connection required
- Session history (last 10 prompts)

## Technical Requirements

### Development

- Kotlin Multiplatform Mobile
- Jetpack Compose for Android UI
- SwiftUI for iOS UI
- MVVM architecture
- Kotlin Coroutines for async operations

### Testing

- Unit tests for business logic
- UI tests for core interactions
- Performance testing for animations

### Performance Metrics

- App size < 20MB
- Startup time < 2 seconds
- Smooth 60fps animations
- Memory usage < 100MB

## Design Guidelines

### Typography

- Headings: Playfair Display
- Body: Source Serif Pro
- Prompts: Baskerville

### Color Palette

- Primary: #121212 (Dark Gray)
- Secondary: #E0E0E0 (Light Gray)
- Accent: #BB86FC (Purple)
- Surface: #1E1E1E
- Error: #CF6679

### Interactions

- Tap anywhere to generate new prompt
- Swipe left/right to review history
- Long press to save favorite prompts

## Deployment Requirements

### App Store

- Screenshots for various device sizes
- App description and keywords
- Privacy policy
- Support contact information

### Play Store

- Feature graphic
- Screenshots for various device sizes
- App description and keywords
- Privacy policy
- Support contact information
