# Use

Things I am using — hardware, software, and the stack I build with every day.

Inspired by [antfu.me/use](https://antfu.me/use). My editor config lives in this repo:
[`settings.json`](./settings.json) · [`extensions.json`](./extensions.json).

> Items marked `TODO` are not filled in yet.

## Hardware

- **Laptop**: MacBook Air 13" M1 · 16GB · macOS 26
- **Phone**: TODO
- **Monitor**: TODO
- **Keyboard**: TODO
- **Mouse**: TODO
- **Headphones**: TODO
- **Desk / Chair**: TODO

## Development

### Editor

- **Editor**: [Cursor](https://cursor.com) — settings & extensions backed up in this repo
- **Theme**: [One Dark Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme)
- **Font**: [Monaspace Argon](https://monaspace.githubnext.com/) with ligatures (`ss01` `ss02` `ss06`)
- **File Icons**: [File Icons](https://marketplace.visualstudio.com/items?itemName=file-icons.file-icons)
- **Product Icons**: [Carbon Icons](https://marketplace.visualstudio.com/items?itemName=antfu.icons-carbon)
- **Linting**: ESLint, fixed on save · Prettier for non-JS files
- **Other IDEs**: Xcode, Android Studio — native builds only

Extension picks worth calling out: [GitLens](https://gitlens.amod.io/),
[Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph),
[Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens),
[i18n Ally](https://github.com/lokalise/i18n-ally),
[Iconify IntelliSense](https://marketplace.visualstudio.com/items?itemName=antfu.iconify),
[Goto Alias](https://marketplace.visualstudio.com/items?itemName=antfu.goto-alias).

### Stack

- **Language**: TypeScript · Kotlin / Swift when the bridge needs it
- **Mobile**: React Native 0.84 + React 19 — my main surface these days
- **Web**: Vue 3 + Vite · uni-app for mini programs
- **State / Data**: Zustand
- **Backend**: Java 17 (Spring Boot) · Prisma + Node for smaller services
- **Runtime**: Node 22 · pnpm as the only package manager
- **Design**: Figma → code, with an in-house design system

### CLI

- **Shell**: zsh
- **Search**: [ripgrep](https://github.com/BurntSushi/ripgrep) · [jq](https://jqlang.github.io/jq/) for JSON
- **Git**: git CLI + [gh](https://cli.github.com/)
- **Mobile release**: fastlane · CocoaPods · Gradle
- **Network debugging**: [mitmproxy](https://mitmproxy.org/)

### AI

- **Daily driver**: Cursor Agent — rules in `.cursor/rules`, skills in `.cursor/skills`
- **How I use it**: root-cause first, no workaround patches; agents read the file from
  disk before editing, and confirm before risky or wide-reaching changes
- **MCP**: Figma for design-to-code
- **Commit messages**: Conventional Commits prefix in English, body in Chinese

## Browser

- **Daily**: Google Chrome · Safari for Apple things · Firefox for testing
- **Extensions**: TODO

## Apps

- **Design**: [Figma](https://figma.com) · Axure RP for wireframes
- **Chat**: Lark · WeChat · Telegram
- **Meetings**: Tencent Meeting
- **Database**: Navicat Premium
- **Recording**: [OBS](https://obsproject.com/)
- **Media**: VLC · Elmedia
- **Networking**: Clash Verge
- **Utilities**: Scroll Reverser · Apple Configurator · Transporter

## This Repo

```bash
# restore settings
cp settings.json "$HOME/Library/Application Support/Cursor/User/settings.json"

# restore extensions
jq -r '.extensions[].id' extensions.json | xargs -L1 cursor --install-extension

# back up again
cp "$HOME/Library/Application Support/Cursor/User/settings.json" settings.json
cursor --list-extensions --show-versions
```

If `cursor` is not on your `PATH`, use
`/Applications/Cursor.app/Contents/Resources/app/bin/cursor`.
