# Welcome to Easy Meets!

Welcome to EasyMeets! This is  documentation for easy-meets,
This readme explains several aspects of the code base for easy-meets, and makes it easier for 
new developers to get started with the project.

!!! note
    We are currently in the process of migrating our documentation to MkDocs.

## Getting Started

???+ tip
    This project can also be found on our [Github Pages](https://easy-meets.github.io/easy-meets-docs/)
    and [Github Repo](https://github.com/easymeets/easymeets)

### Prerequisites

- Node.js
- Expo CLI
- Windows, macOS, or Linux
- Android Studio (for Android development)
- Xcode (for iOS development)
- Expo client (for running the app on a physical device)
- Expo Go (for running the app on an emulator)
- Git


### Installation

!!! info
    If you have any trouble setting up the project, send an email to easymeetsnyc@gmail.com and we can help you out!

- Clone the project repository from the source control system (e.g. GitHub) to the new machine. You can do this by running the following command in the terminal:

   ```
   git clone <repository-url>
   ```

   Replace `<repository-url>` with the URL of the repository.

- Navigate to the project directory by running the following command in the terminal:

   ```
   cd <project-directory>
   ```

   Replace `<project-directory>` with the name of the project directory.

- Install the required dependencies by running the following command in the terminal:

   ```
   npm install yarn --global
   yarn install
   ```

   This will install all the dependencies listed in the `package.json` file. (Will take a decent time to download)

- Ensure that the new machine has the required environment setup. This project requires Node.js and Expo CLI to be installed. You can download and install Node.js from the official website (https://nodejs.org/en/download/) and install Expo CLI by running the following command in the terminal:

   ```
   yarn global add expo-cli
   ```

- Run the project using the following command in the terminal:

   ```
   yarn start
   ```

   This will start the development server and open the Expo client in your default web browser. You can then use the Expo client to run the app on a physical device or emulator.


## Tech Stack

**Frontend:** React-Native, React-Paper, TailwindCSS

**Backend:** Supabase

**Deployment:** Vercel, Android App Store, IOS app store


[Link to MkDocs Docs](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/)


## FAQ

### How do I add a new page to the documentation?

1. **Create a new Markdown file**: In the easy meets repo, create a new Markdown file in the `docs` directory. This file will represent your new page. For example, you might create a file called `new_page.md`.

2. **Write your content**: Open the new Markdown file and write your content. You can use any standard Markdown syntax.

3. **Update the navigation**: To make your new page accessible, you need to add it to the navigation structure. This is done in the `mkdocs.yml` file, which is located in the root of your project. Open this file and look for the `nav` or `pages` section (depending on your MkDocs version). Add a new entry for your page. For example:

```yaml

nav:
  - 'Home': 'index.md'
  - 'New Page': 'new_page.md'

```

### I am running into the "SupabaseURL not defined" error. How do I fix this?

This error occurs when the SupabaseURL is not defined in the environment variables. Contact easymeetsnyc@gmail.com for the SupabaseURL environment variable or file.
