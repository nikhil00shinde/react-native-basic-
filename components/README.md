## Navigtion
- It is quite different than the react navigation, in react native the we have stack, modal and tabs navigation.
- The filename-to-URL mapping is more obvious on the web.
- The key to making it work is **_layout** routes. Each folder may have exactly one layout route and it will dictate how the files in the route get laid out.

We use `npx expo install` to install package because it is more download the best compatible version for the sdk.


In package.json, we have `main` key which defined the entry point of the application.

We need to add `scheme` - expo-router comes with the deep linking, (creating an URL to open an app to spefic screen).
The way deep linking work on mobile app, register to a specific scheme. Every app has their own `scheme`, which tell the url is related to me.

```
{
  "scheme": "taskly"
}
```

Handy command `yarn start --reset-cache`


#### Different types of navigation

##### Stack Navigation
- By default, everything rendered in a stack. And it means that when navigate onto a new screen, it renders on top of the old, new screens renders on top of the old screen, we have a stack.

Displaying screens in a Stack is the default way to navigate. It means that when you navigate to a new screen, it is rendered on top of the current screen, so you can `goBack()` to the previous screen to go back.

- Ways to navigate
There are 3 main ways to navigate between screens:
   - Using the `Link` component
   - Programmatically with the `useRouter` hook
   - Using the built-in header and bottom tabs button

##### Modal Navigation
- Modal means rendering it on top of other content. It's important to note that in order for this to work, the modal screen must be defined *above* or *adjacent* to the other screens it's being rendered on top of.
To render a screen modally, use `presentation: "modal"` in its screen options.
- `animation: "fade" || "flip"` to mention the modal animation

##### Bottom tab navigation
The bottom tab navigation means rendering the screens (or stacks of screens!) as bottom tabs where the tabs are always visible so you can easily switch between them.

With Expo Router, simply change the `Stack` in your layout file the `Tabs`.
- Use `tabBarIcon: ({color,size}) => ()` to return the icon that you want to render, 
- In the parent `Tabs` you can add `screenOptions={{ tabBarActiveColor: theme.colorCerulean}}`