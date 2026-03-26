# Artifact

A Java 2D platformer project with a standard source/resources layout for easier maintenance and IDE import.

## Project Structure

```text
Artifact/
├── docs/                    # Project documentation and presentation assets
├── libs/                    # Third-party JAR dependencies
├── src/
│   └── main/
│       ├── java/            # Java source code (packages under com.neet)
│       └── resources/
│           ├── audio/
│           │   ├── music/
│           │   └── sfx/
│           ├── images/
│           │   ├── backgrounds/
│           │   ├── sprites/
│           │   └── tilesets/
│           ├── maps/
│           └── ui/
├── .gitignore
└── README.md
```

## Requirements

- JDK 8+ (tested with standard `javac`/`java` workflow)

## Run (CLI)

From the repository root:

```bash
mkdir -p out
javac -cp "libs/*" -d out $(find src/main/java -name "*.java")
cp -R src/main/resources/* out/
java -cp "out:libs/*" com.neet.Main.Game
```

> On Windows PowerShell/CMD, use `;` instead of `:` in the `java -cp` command.

## Run (IDE)

1. Open/import this folder as a Java project.
2. Mark `src/main/java` as Sources Root.
3. Mark `src/main/resources` as Resources Root (or ensure resources are on classpath).
4. Add all JARs in `libs/` to the project classpath.
5. Run `com.neet.Main.Game`.

## Controls

- Move: Left / Right arrows
- Jump: `W`
- Attack: `R`
- Dash: `F`

## Notes

- Resource paths in code were updated to match `src/main/resources`.
- Existing Java packages remain `com.neet.*` to keep refactor low-risk.
- Suggested future package cleanup (optional):
  - `game.core`
  - `game.entity`
  - `game.level`
  - `game.ui`
  - `game.audio`
  - `game.utils`
