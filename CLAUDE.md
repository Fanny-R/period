# Period tracker

Personal Android app: records period start dates locally, computes the average cycle length and predicts the next period.

## Commands
- Build: `./gradlew assembleDebug`
- Unit tests: `./gradlew testDebugUnitTest`
- Lint: `./gradlew lint`

## Architecture
- Kotlin + Jetpack Compose, single activity
- Domain logic in `domain/`: plain Kotlin, no Android imports, fully unit-tested
- UI state in ViewModels; persistence with Room (added later)

## Rules
- Data stays on the device: never add the INTERNET permission or any network library
- Run the unit tests after changing anything in `domain/`
- Prefer small, focused changes; explain any new dependency before adding it

## Data sensitivity
This is intended to be a period-tracking app, which means it will store health data. The manifest has `allowBackup="true"`, with rules in `res/xml/backup_rules.xml` and `res/xml/data_extraction_rules.xml`. Review those when you add persistent storage.
