```bash
git clone git@github.com:brillout/vite-4-2-0-beta_VPS_reprod
cd vite-4-2-0-beta_VPS_reprod/
pnpm install
pnpm run dev
```

Same as single line (copy-paste me):

```shell
git clone git@github.com:brillout/vite-4-2-0-beta_VPS_reprod && cd vite-4-2-0-beta_VPS_reprod/ && pnpm install && pnpm run dev
```

BEFORE you go to `localhost:3000` make sure you enable the `Perserve log` checkbox in Chrome's dev console.

Also make sure to run with a clean Vite cache `$ rm -rf node_modules/.vite/`.

Now go to [localhost:3000](http://localhost:3000) and observe the errors. The first/root error being:

```
Warning: Invalid hook call. Hooks can only be called inside of the body of a function component. This could happen for one of the following reasons:
1. You might have mismatching versions of React and the renderer (such as React DOM)
2. You might be breaking the Rules of Hooks
3. You might have more than one copy of React in the same app
See https://reactjs.org/link/invalid-hook-call for tips about how to debug and fix this problem. 
    at Counter (http://localhost:3000/pages/index/Counter.jsx:21:29)
    at li
    at ul
    at Page
    at div
    at Content (http://localhost:3000/renderer/PageLayout.jsx:88:3)
    at div
    at Layout (http://localhost:3000/renderer/PageLayout.jsx:56:3)
    at PageLayout (http://localhost:3000/renderer/PageLayout.jsx:20:3)
```

Note that after Vite discovers and optimizes React:

```
12:19:50 AM [vite] ✨ new dependencies optimized: react-dom/client
12:19:50 AM [vite] ✨ optimized dependencies changed. reloading
```

The page is reloaded, the error is gone, and the app works as expected. To reproduce the error you'll have to clean Vite's cache `$ rm -rf node_modules/.vite/`.
