# SwiftOS
An intelligent OS for digital sovereignty

## Team
Key collaborators from the swift forums
* [@MinerMinerMain](https://forums.swift.org/u/minerminermain)
* [@RandomHashTags](https://forums.swift.org/u/randomhashtags)
* [@zamderax](https://forums.swift.org/u/zamderax)
* development at [schwiftyos](https://github.com/orgs/schwiftyos/repositories)
# Problem
what problem are we trying to solve? How can this be 10x better?
## I want…
* The Apple iCloud ecosystem experience without Apple pricing and forever subscriptions
* The Apple hardware ecosystem but without restrictions, mix and match
* Using a computer to be 10x simpler - less clicks, less redundant apps
* Developing apps to be 10x simpler - the OS should handle the UI, dev just handle business logic

### I want the Apple ecosystem experience without having to pay Apple prices
* I want a kickass computer without insane Apple SSD pricing
* I want my stuff synced, secure, private, and stable, without constantly paying cloud subscription fees
* I want the benefits of a walled garden (close hardware software integration) without the gate being locked by someone else; I want to hold the keys myself (decentralization)
* everythig just works, without paying subscriptions forever
### I want a hardware ecosystem like Apple’s without the restrictions, and lock in
* I want to be able to mix and match and still have everything work seemless together
  * maybe an Apple MacBook with an Android phone and a custom desktop PC
* I want one computer for games and work
  * right now, windows for games, mac for work; I just want one system that excels at both
* I think a Razor Laptop should be our first target device https://www.razer.com/gaming-laptops/razer-blade-16
* Running on MacBook Pros would also be cool later, work with Asahi Linux
* Smartphone: something like[CMF Phone 1](https://us.nothing.tech/products/cmf-phone-1)
* Smartwatch:  https://us.nothing.tech/products/cmf-watch-pro-2
* Tablet:  [Daylight | A More Caring Computer](https://daylightcomputer.com/)
### I want using a computer to be 10x easier
* too many apps! it went from being cool to overwhelming
  * less redundant apps; everything should be like Notion, but with a more flexible UI handled by the OS, not the app
* AI apps should focus on jobs to be done, (e.g. messaging) instead of the app service or brand (e.g. Discord, Slack, etc.)
  * one UX theme, but the API and business logic can be swapped out
  * the UX theme is customizable and controlable by the OS, not the app developer
    * so its consistent
* less clicking, less repititive tasks
### I want developing apps to be 10x easier
* even the latest UI frameworks, SwiftUI, Svelte, React, are a pain. So many devs are writing the same List view over and over again
* the OS should handle the UI, devs handle the business logic
  * and the AI agent logic, coordinate with system AI
* It should be as easy as streamlit to coordinate widgets with business logic, and let the OS and LLM handle the rest [Streamlit • A faster way to build and share data apps](https://streamlit.io/)

# Solution: Desktop + App Experience
Tagline: **An intelligent OS for digital sovereignty**
Big idea: **Composable agents and widgets over isolated apps**
* On demand widgets mixed together from the LLM
* App downloads will be smaller and UI libraries simpler
* Apps should work with Hyprland, this is our desktop environment [Dynamic tiling window compositor with the looks](https://hyprland.org/)
### Outline
#### Composable Widgets and Types: Shared data layer
data layer is shared across all apps, they can request access, but they cannot create their own silo data
* everything should work like Notion / AnyType / Craft / Capacities
* the entire OS should have this shared knowledge, but the UI needs to be more flexible than those apps
#### Decentralized services
Avoid cloud subscriptions with open source, decentralized sync and backup built in
* **Accounts** - Apple ID
* **Data Sync** - iCloud Storage for data and photos
* **Messaging** - iMessage
* **Social Media** - Facebook / X etc.
* **Payments** - Apple Wallet / Paypal 
* **Packages** - AppStore + AUR / SwiftPackageIndex
#### Universal AI chat history
shared history from all chat agents with the OS LLM, and when that LLM hands off tasks to other LLMs
#### Performant AI engine
On device LLM Inference powered by Modular Max Engine [A Fast, Scalable Gen AI Inference Platform](https://www.modular.com/)
* integrated deep in the core of the OS
* not in the kernel, but at the root of user space
## Composable Widgets and Types
* instead of windows, want to think in widgets
* the OS handles the UI, devs only need to write business logic
  * the OS theme can be customized by the user, its adaptive but consistent
  * everything should be like composable Notion / AnyType / Canva / Craft / NotePlan
* The OS provides a set of Core Widgets and Core Types https://doc.anytype.io/anytype-docs/basics/types from which the LLM (or 3rd party developer writing an “app”) composes depending o the task at hand
* Core Widgets (UI)
  * Library
  * Doc
  * Table
  * Calendar
  * Map
  * Communicator
  * 2D Canvas
  * 3D Canvas
  * Immersive
  * Web
  * Custom (Legacy apps)
* Core Types (Data)
  * Task
  * Note
  * Book
  * Movie
  * Idea
  * Person
  * Custom
  * etc.

* Remember everything is composable, you could have a table full of docs, or a doc with embedded tables. 
* Furthermore tasks could be in a kanban table, or spread out alongside docs on a 2D canvas; the data is always in sync, its just different views for the same data

### Library
* library: file / media browser (finder + photos behavior)
* the library is the list for all types and other widgets; show tasks, notes, books, as well as docs, tables (each containing types) along side each other
### Doc
* read (text, ebooks, pdfs, etc.)
  * read only prevents accidental editing
* write (text, presentations, todos, code)
  * one click publish as website or send as email
* programming
  * this is where the IDE lives, its just a special Doc
  * its like VS Code, Swift Playgrounds, all in one
  * switch between modes for different dev environments
  * download 3rd party extensions for new tools and frameworks
* composable, embed other widgets like tables, maps, etc.
* markdown and block based
  * switch between different markdown renderers or styles on the fly
  * download 3rd party extensions or renders as needed
### Table
* tables (spreadhseets, excel, etc)
* tasks
  * while they can live in docs, they can also have their own dedicated table or kanban view
### Calendar
* calendar, work with existing calendars like Gmail, etc.
* all time related views
  * day, week, month, year
  * world clock, timers, etc.
* scheduling - integrate with Cal.com
### Map
* map data and UI from 3rd parties 
  * Google, Apple, or Mapbox
  * mix and match
* compose layers on top with your other types, notes, pictures, whatever
### Communicator
* all forms of communication (chat, email, video calls, etc.)
* composable with Docs for email, both reading and writing
  * use markdown to write emails like [MailMate](https://freron.com/)
  * integrate with gmail like https://mimestream.com/
* contacts show up as a composable Library widget
  * has built in CRM functionality, and updates from all social media sources
  * like https://www.busymac.com/busycontacts/ or [Clay](https://clay.earth/)
* also integrate with social media, both decentralized and traditional
* show web views if needed
### 2D Canvas
* canvas 2D can be composed with any other widget or type
  * its like Figma or Apple Freeform all in one
  * use for design or notes, like how Craft works
### 3D Canvas
* canvas 3D also composable with your types and widgets
* switch between 3rd party renderers and menu extensions as needed
  * like unreal engine, unity, blender, maya, etc.
  * but consistent UI
### Immersive
* games, full screen
* XR experiences
### Web
* browse the web, not much changes, use Orion or Ladybird
* this can also be a way to run legacy apps, ie chromeOS
### Custom (Legacy apps)
* custom, for particular pro apps 
* IDEs, Video editing, music editing
* as time goes on, ideally this would no longer be needed
  * devs will write their business logic into the composable OS system
  * saves them time and money once adoption hits critical mass

### List of things Notion alternatives should have
A good reminder of core features we should have too
[5 Privacy-Focused Notion Alternatives That I Tried!](https://itsfoss.com/notion-alternatives/)
* Local-first
* Open Source
* Note-taking / Journal
* AI assistant (paid unlocks more usage)
* Self-host
* Android and iOS apps
* Templates
* Collaboration (cloud)
* Calendar
* Two-factor Authentication (cloud) (or nowadays passkeys)
* Google Drive/Slack connections
* Notion import

## Decentralization
how should it play well with others?
* We need to make decentralized services as easy to use as Apple services
* Our desktop UI and account settings should connect all these together in a seamless way
#### We need decentralized versions of
* **Accounts** - Apple ID
* **Data Sync** - iCloud Storage for data and photos
* **Messaging** - iMessage
* **Social Media** - Facebook / X etc.
* **Payments** - Apple Wallet / Paypal 
* **Packages** - AppStore + AUR / SwiftPackageIndex
### Accounts
* Each local account also is attached to an AnyType Account https://anytype.io/
* the file system leverages the anytype object system, so all data is an anytype object
* any app can leverage this kind of “notion” like application, but with our custom UI
* password management - built in, synced and secure, like Apple Passwords
### Data Sync
* user data can sync between user devices via anySync protocol [anyproto/any-sync](https://github.com/anyproto/any-sync)
  * syncthing could be used as well as a more traditional p2p solution [Syncthing](https://syncthing.net/)
  * e.g. anysync can store things across millions of public devices, syncthing only syncs between users devices, but has no redundancy
* user could opt into traditional cloud services if they wanted
  * spin up their own supabase in a click, or just use Dropbox, iCloud etc.
  * use https://objectbox.io/sync/ ?
* photo sharing should be seamless, synced between users devices, and sharable to social media with a click
### Messaging
* the user can connect to their matrix account, creating an iMessage like experience [Matrix.org](https://matrix.org/)
* we should make a client that can switch protocols behind the hood, so one UI, but works with matrix, and via the matrix interopt also Slack, Discord, etc.
### Social Media
* user can connect to a variety of decentralized and traditional social media accounts
* nostr, bluesky, mastadon, X, facebook, insta, threads, etc.
* Default is nostr, try to promote the platform
  * if your not familiar, explore its benefits [Nostr protocol](https://nostr.org/)
  * make an account at https://nostr.com/
  * leverage existing open source clients such as [Damus](https://damus.io/notedeck/) or [Home - Nos: The Human Network](https://www.nos.social/)
### Payments
* user can connnect to payment accounts
  * lightning allows simple bitcoin payments [Lightning Network](https://lightning.network/)
  * traditional accounts like Wise, paypal, Cash, as well
* we will leverage Alby or build something similar to keep accounts coordinated and secure https://getalby.com/developers
* essentially Alby is like Apple Wallet
### Packages
* App Store + package management integrated
* you can buy an app, package, AI agent, whatever, with one click, using payment account above
* Leverage or combine AUR, Swift Package Index, Tuist Swift Registry
  * [Announcing Tuist Registry](https://tuist.dev/blog/2025/01/22/announcing-tuist-registry)
* Why combine packages and apps?
  * AI apps will be fundamentally different; e.g. UX is handled by the OS, the “app” just handles business logic, and the LLM coordinates or users what is has access to based on user request
  * also AI may need to access new packages
  * streamline and blur the line between composable swift code and fully ready “apps”
  * AI may grab a swift package, to run and compile an app just for a users specific, one time, request
