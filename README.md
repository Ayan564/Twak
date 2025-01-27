<a name="readme-top"></a>

# Twak - A Real-Time Messaging App using Next.js 14.

<!-- Table of Contents
<details>
<summary>

# Table of Contents

</summary>

- [Folder Structure](#bangbang-folder-structure)
- [Getting Started](#toolbox-getting-started)
- [Screenshots](#camera-screenshots)
- [Tech Stack](#gear-tech-stack)
- [Acknowledgements](#gem-acknowledgements)
- [Deploy on Vercel](#page_with_curl-deploy-on-vercel)

</details> -->

## Folder Structure

Here is the folder structure of this app.

```bash
messenger-clone/
  |- app/
    |-- (site)/
        |--- components/
        |--- page.tsx
    |-- actions/
        |--- get-conversation-by-id.ts
        |--- get-conversation.ts
        |--- get-current-user.ts
        |--- get-messages.ts
        |--- get-session.ts
        |--- get-users.ts
    |-- api/
        |--- auth/[...nextauth]/
            |---- route.ts
        |--- conversations/[conversationId]/
            |---- seen/
                |----- route.ts
            |---- route.ts
        |--- route.ts
        |--- messages/
            |---- route.ts
        |--- register/
            |---- route.ts
        |--- settings/
            |---- route.ts
    |-- components/
        |--- inputs/
            |---- input.tsx
            |---- select.tsx
        |--- modals/
            |---- modal.tsx
            |---- settings-modal.tsx
        |--- sidebar/
            |---- desktop-item.tsx
            |---- desktop-sidebar.tsx
            |---- mobile-footer.tsx
            |---- mobile-item.tsx
            |---- sidebar.tsx
        |--- active-status.tsx
        |--- avatar-group.tsx
        |--- avatar.tsx
        |--- button.tsx
        |--- empty-state.tsx
        |--- loading-modal.tsx
    |-- config/
        |--- authOptions.tsx
        |--- site.ts
    |-- context/
        |--- auth-context.ts
        |--- toaster-context.ts
    |-- conversations/
        |--- [conversationId]/
            |---- components/
                |----- conversation-box.tsx
                |----- conversation-list.tsx
                |----- group-chat-modal.tsx
        |--- layout.tsx
        |--- loading.tsx
        |--- page.tsx
    |-- hooks/
        |--- use-active-channel.tsx
        |--- use-active-list.tsx
        |--- use-conversation.tsx
        |--- use-other-user.tsx
        |--- use-routes.tsx
    |-- libs/
        |--- prismadb.ts
        |--- pusher.ts
    |-- types/
        |--- index.ts
    |-- users/
        |--- components/
            |---- user-box.tsx
            |---- user-list.tsx
        |--- layout.tsx
        |--- loading.tsx
        |--- page.tsx
    |-- favicon.ico
    |-- globals.css
    |-- layout.tsx
  |-- pages/
   |-- api/
    |-- pusher/
     |-- auth.ts
  |- prisma/
    |-- schema.prisma
  |- public/
    |-- images/
        |--- logo.png
        |--- placeholder.jpg
  |- .env
  |- .eslintrc.json
  |- .gitignore
  |- middleware.ts
  |- next.config.js
  |- package-lock.json
  |- package.json
  |- postcss.config.js
  |- tailwind.config.ts
  |- tsconfig.json
```

<br />

## Getting Started

1. Make sure **Git** and **NodeJS** is installed.
2. Clone this repository to your local computer.
3. Create `.env` file in root directory.
4. Contents of `.env`:

```bash
# .env

# mongodb url
DATABASE_URL="mongodb://127.0.0.1/messenger-clone"

# client url for next auth
NEXTAUTH_URL=http://localhost:3000

# next auth secret (random strings)
NEXTAUTH_SECRET=<your-nextauth-secret>

# github auth credentials
GITHUB_CLIENT_ID=<your-github-client-id>
GITHUB_CLIENT_SECRET=<your-github-client-secret>

# google auth credentials
GOOGLE_CLIENT_ID=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=<your-google-client-secret>

# next cloudinary credentials
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=xxxxxxxxx
NEXT_PUBLIC_CLOUDINARY_CLOUD_PRESET=xxxxxxxxxx

# pusher credentials
PUSHER_APP_ID=00000000
PUSHER_APP_SECRET=xxxxxxxxxxxxxxxxxxxxxx
NEXT_PUBLIC_PUSHER_APP_KEY=xxxxxxxxxxxxxxxxxxxxx
NEXT_PUBLIC_PUSHER_APP_CLUSTER=xxx

```

5. **MongoDB URL**

   - Install and run MongoDB locally or use a cloud-based MongoDB service.
   - Replace the placeholder in `DATABASE_URL` with your actual MongoDB connection string.

6. **NextAuth Configuration**

   - Set up NextAuth by following the official documentation: [NextAuth.js Documentation](https://next-auth.js.org/getting-started/introduction)
   - Set `NEXTAUTH_URL` to the base URL of your application.
   - Generate a random string for `NEXTAUTH_SECRET`.

7. **GitHub Auth**

   - Create a GitHub OAuth App by following the guide: [Creating an OAuth App](https://docs.github.com/en/developers/apps/creating-an-oauth-app)
   - Set `GITHUB_CLIENT_ID` and `GITHUB_CLIENT_SECRET` with the obtained credentials.

8. **Google Auth**

   - Create a project on the Google Cloud Console: [Google Cloud Console](https://console.cloud.google.com/)
   - Follow the steps to set up OAuth consent screen and credentials: [Create credentials](https://developers.google.com/identity/sign-in/web/sign-in)
   - Set `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET` with the obtained credentials.

9. **Cloudinary**

   - Sign up for a Cloudinary account: [Cloudinary Sign-up](https://cloudinary.com/users/register/free)
   - Retrieve your cloud name from the dashboard.
   - Set `NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME` and `NEXT_PUBLIC_CLOUDINARY_CLOUD_PRESET` with the obtained credentials.

10. **Pusher**

    - Sign up for a Pusher account: [Pusher Sign-up](https://dashboard.pusher.com/accounts/sign_up)
    - Create a new app and obtain the app ID, app secret, app key, and cluster.
    - Set `PUSHER_APP_ID`, `PUSHER_APP_SECRET`, `NEXT_PUBLIC_PUSHER_APP_KEY`, and `NEXT_PUBLIC_PUSHER_APP_CLUSTER` with the obtained credentials.

11. Open terminal in root directory. Run `npm install` or `yarn install`.

12. Now app is fully configured 👍 and you can start using this app using `npm run dev` or `yarn dev`.

### Additional Resources

- **Next.js Documentation:** Explore the power of Next.js for building your web applications.

  - [Next.js Documentation](https://nextjs.org/docs/)

- **NextAuth.js Documentation:** Learn more about authentication in Next.js using NextAuth.js.

  - [NextAuth.js Documentation](https://next-auth.js.org/)

- **Tailwind CSS Documentation:** Dive into the documentation for Tailwind CSS, a utility-first CSS framework used in the project.

  - [Tailwind CSS Documentation](https://tailwindcss.com/docs)

- **Pusher Documentation:** Explore Pusher for adding real-time functionality to your applications.

  - [Pusher Documentation](https://pusher.com/docs)

- **React Icons Documentation:** Find and customize high-quality SVG icons for your React applications.

  - [React Icons Documentation](https://react-icons.github.io/react-icons/)

- **React Select Documentation:** Get to know more about React Select, a flexible and customizable select component.

  - [React Select Documentation](https://react-select.com/home)

- **React Hook Form Documentation:** Learn about React Hook Form for efficient form management in React.

  - [React Hook Form Documentation](https://react-hook-form.com/get-started)

- **Next Cloudinary Documentation:** Understand how to integrate Cloudinary for image and video management.

  - [Next Cloudinary Documentation](https://cloudinary.com/documentation)

- **Prisma Documentation:** Explore Prisma for database access in TypeScript and JavaScript.

  - [Prisma Documentation](https://www.prisma.io/docs/)

- **Axios Documentation:** Find information on how to use Axios for making HTTP requests.

  - [Axios Documentation](https://axios-http.com/docs/intro)

- **Zustand Documentation:** Learn about Zustand, a small and fast state management library.

  - [Zustand Documentation](https://zustand.surge.sh/)

- **React Hot Toast Documentation:** Understand how to use React Hot Toast for toast notifications in React applications.

  - [React Hot Toast Documentation](https://react-hot-toast.com/)

- **Headless UI Documentation:** Explore Headless UI, a set of completely unstyled UI components.
  - [Headless UI Documentation](https://headlessui.dev/)

**NOTE:** Please make sure to keep your API keys and configuration values secure and do not expose them publicly.

## Screenshots:

![Modern UI/UX](/public/images/modern-uiux.png "Modern UI/UX")

![Realtime Messaging](/public/images/realtime-messeging.png "Realtime Messaging")

![Create Group Chats](/public/images/group-chat.png "Create Group Chats")

![Edit your Profile](/public/images/update-profile.png "Edit your Profile")

## Tech Stack

[![React JS](https://skillicons.dev/icons?i=react "React JS")](https://react.dev/ "React JS") [![Node](https://skillicons.dev/icons?i=nodejs "Node")](https://react.dev/ "Node") [![Typescript](https://skillicons.dev/icons?i=ts "Typescript")](https://www.typescriptlang.org/ "Typescript") [![Next JS](https://skillicons.dev/icons?i=next "Next JS")](https://nextjs.org/ "Next JS") [![Tailwind CSS](https://skillicons.dev/icons?i=tailwind "Tailwind CSS")](https://tailwindcss.com/ "Tailwind CSS") [![MongoDB](https://skillicons.dev/icons?i=mongodb "MongoDB")](https://nextjs.org/ "MongoDB") [![Prisma](https://skillicons.dev/icons?i=prisma "Prisma")](https://prisma.io/ "Prisma") [![Vercel](https://skillicons.dev/icons?i=vercel "Vercel")](https://vercel.app/ "Vercel")

## Acknowledgements

Useful resources and dependencies that are used in Twak.

- [@headlessui/react](https://www.npmjs.com/package/@headlessui/react) - Version: ^1.7.17
- [@next-auth/prisma-adapter](https://www.npmjs.com/package/@next-auth/prisma-adapter) - Version: ^1.0.7
- [@prisma/client](https://www.npmjs.com/package/@prisma/client) - Version: ^5.7.0
- [@tailwindcss/forms](https://www.npmjs.com/package/@tailwindcss/forms) - Version: ^0.5.7
- [axios](https://www.npmjs.com/package/axios) - Version: ^1.6.2
- [bcrypt](https://www.npmjs.com/package/bcrypt) - Version: ^5.1.1
- [clsx](https://www.npmjs.com/package/clsx) - Version: ^2.0.0
- [date-fns](https://www.npmjs.com/package/date-fns) - Version: ^2.30.0
- [lodash](https://www.npmjs.com/package/lodash) - Version: ^4.17.21
- [next](https://www.npmjs.com/package/next) - Version: 14.0.3
- [next-auth](https://www.npmjs.com/package/next-auth) - Version: ^4.24.5
- [next-cloudinary](https://www.npmjs.com/package/next-cloudinary) - Version: ^5.11.0
- [pusher](https://www.npmjs.com/package/pusher) - Version: ^5.2.0
- [pusher-js](https://www.npmjs.com/package/pusher-js) - Version: ^8.4.0-rc2
- [react](https://www.npmjs.com/package/react) - Version: ^18
- [react-dom](https://www.npmjs.com/package/react-dom) - Version: ^18
- [react-hook-form](https://www.npmjs.com/package/react-hook-form) - Version: ^7.48.2
- [react-hot-toast](https://www.npmjs.com/package/react-hot-toast) - Version: ^2.4.1
- [react-icons](https://www.npmjs.com/package/react-icons) - Version: ^4.12.0
- [react-select](https://www.npmjs.com/package/react-select) - Version: ^5.8.0
- [react-spinners](https://www.npmjs.com/package/react-spinners) - Version: ^0.13.8
- [zustand](https://www.npmjs.com/package/zustand) - Version: ^4.4.7
- [@types/bcrypt](https://www.npmjs.com/package/@types/bcrypt) - Version: ^5.0.2
- [@types/lodash](https://www.npmjs.com/package/@types/lodash) - Version: ^4.14.202
- [@types/node](https://www.npmjs.com/package/@types/node) - Version: ^20
- [@types/react](https://www.npmjs.com/package/@types/react) - Version: ^18
- [@types/react-dom](https://www.npmjs.com/package/@types/react-dom) - Version: ^18
- [autoprefixer](https://www.npmjs.com/package/autoprefixer) - Version: ^10.0.1
- [eslint](https://www.npmjs.com/package/eslint) - Version: ^8
- [eslint-config-next](https://www.npmjs.com/package/eslint-config-next) - Version: 14.0.3
- [postcss](https://www.npmjs.com/package/postcss) - Version: ^8
- [prisma](https://www.npmjs.com/package/prisma) - Version: ^5.7.0
- [tailwindcss](https://www.npmjs.com/package/tailwindcss) - Version: ^3.3.0
- [typescript](https://www.npmjs.com/package/typescript) - Version: ^5

<!-- ## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details. -->
