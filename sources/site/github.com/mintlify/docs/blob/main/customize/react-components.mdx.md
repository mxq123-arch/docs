# Source: https://github.com/mintlify/docs/blob/main/customize/react-components.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# react-components.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/customize/react-components.mdx)

History

267 lines (220 loc) · 9.32 KB

## FilesExpand file tree

 main

/

# react-components.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

267 lines (220 loc) · 9.32 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/customize/react-components.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>React</td></tr><tr><th>description</th><td>Build interactive and reusable elements with custom React components in your Mintlify documentation using JSX, state, and client-side logic.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">React components</div></th><th><div dir="auto">interactive components</div></th><th><div dir="auto">JSX</div></th><th><div dir="auto">custom components</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

import { ColorGenerator } from "/snippets/color-generator.jsx";

Build interactive elements in your docs using [React components](https://react.dev) and [hooks](https://react.dev/reference/react/hooks) directly in MDX files.

## Inline components

Declare components directly in your MDX file:

export const Counter = () => { const \[count, setCount\] = useState(0)

const increment = () => setCount(count + 1) const decrement = () => setCount(count - 1)

return (

\-

```
    <div className="flex text-sm items-center justify-center h-8 px-6 text-zinc-950/80 dark:text-white/80 font-medium min-w-[4rem] text-center">
      {count}
    </div>

    <button
      onClick={increment}
      className="flex items-center justify-center h-8 w-8 text-zinc-950/80 dark:text-white/80 border-l border-zinc-950/20 dark:border-white/20"
      aria-label="Increase"
    >
      +
    </button>
  </div>
</div>
```

) }

```mdx
export const Counter = () => {
  const [count, setCount] = useState(0)
  const increment = () => setCount(count + 1)
  const decrement = () => setCount(count - 1)

  return (
    <div>
      <button onClick={decrement}>-</button>
      <span>{count}</span>
      <button onClick={increment}>+</button>
    </div>
  )
}

<Counter />
```

## Constraints

React components in Mintlify run in a sandboxed MDX environment with the following constraints:

- **React hooks are pre-injected**: `useState`, `useEffect`, `useRef`, `useCallback`, `useMemo`, `useContext`, and `useReducer` are available without importing them.
- **No external npm packages**: Third-party packages (for example, `lodash`, `axios`, `date-fns`) cannot be imported. Use browser built-ins or write the logic inline.
- **No default exports**: Use named exports (`export const MyComponent = ...`). Default exports (`export default`) are not supported.
- **No cross-snippet imports**: Snippet files cannot import other snippet files. Import all dependencies directly in the parent MDX file.
- **No JSON imports**: Importing `.json` files is not supported.

## Import components

Component files must be in the `/snippets/` folder. Learn more about [reusable snippets](https://github.com/mintlify/docs/blob/main/create/reusable-snippets).

Nested imports are not supported. Import all referenced components directly into the parent MDX file.

Create a component file in `snippets/`:

```mdx
export const ColorGenerator = () => {
  const [hue, setHue] = useState(180)
  const [saturation, setSaturation] = useState(50)
  const [lightness, setLightness] = useState(50)
  const [colors, setColors] = useState([])

  useEffect(() => {
    const newColors = []
    for (let i = 0; i < 5; i++) {
      const l = Math.max(10, Math.min(90, lightness - 20 + i * 10))
      newColors.push(`hsl(${hue}, ${saturation}%, ${l}%)`)
    }
    setColors(newColors)
  }, [hue, saturation, lightness])

  const copyToClipboard = (color) => {
    navigator.clipboard
      .writeText(color)
      .then(() => {
        console.log(`Copied ${color} to clipboard!`)
      })
      .catch((err) => {
        console.error("Failed to copy: ", err)
      })
  }

  return (
    <div className="p-4 border dark:border-zinc-950/80 rounded-xl not-prose">
      <div className="space-y-4">
        <div className="space-y-2">
          <label className="block text-sm text-zinc-950/70 dark:text-white/70">
            Hue: {hue}°
            <input
              type="range"
              min="0"
              max="360"
              value={hue}
              onChange={(e) => setHue(Number.parseInt(e.target.value))}
              className="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1"
              style={{
                background: `linear-gradient(to right, 
                  hsl(0, ${saturation}%, ${lightness}%), 
                  hsl(60, ${saturation}%, ${lightness}%), 
                  hsl(120, ${saturation}%, ${lightness}%), 
                  hsl(180, ${saturation}%, ${lightness}%), 
                  hsl(240, ${saturation}%, ${lightness}%), 
                  hsl(300, ${saturation}%, ${lightness}%), 
                  hsl(360, ${saturation}%, ${lightness}%))`,
              }}
            />
          </label>

          <label className="block text-sm text-zinc-950/70 dark:text-white/70">
            Saturation: {saturation}%
            <input
              type="range"
              min="0"
              max="100"
              value={saturation}
              onChange={(e) => setSaturation(Number.parseInt(e.target.value))}
              className="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1"
              style={{
                background: `linear-gradient(to right, 
                  hsl(${hue}, 0%, ${lightness}%), 
                  hsl(${hue}, 50%, ${lightness}%), 
                  hsl(${hue}, 100%, ${lightness}%))`,
              }}
            />
          </label>

          <label className="block text-sm text-zinc-950/70 dark:text-white/70">
            Lightness: {lightness}%
            <input
              type="range"
              min="0"
              max="100"
              value={lightness}
              onChange={(e) => setLightness(Number.parseInt(e.target.value))}
              className="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1"
              style={{
                background: `linear-gradient(to right, 
                  hsl(${hue}, ${saturation}%, 0%), 
                  hsl(${hue}, ${saturation}%, 50%), 
                  hsl(${hue}, ${saturation}%, 100%))`,
              }}
            />
          </label>
        </div>

        <div className="flex space-x-1">
          {colors.map((color, idx) => (
            <div
              key={idx}
              className="h-16 rounded flex-1 cursor-pointer transition-transform hover:scale-105"
              style={{ backgroundColor: color }}
              title={`Click to copy: ${color}`}
              onClick={() => copyToClipboard(color)}
            />
          ))}
        </div>

        <div className="text-sm font-mono text-zinc-950/70 dark:text-white/70">
          <p>
            Base color: hsl({hue}, {saturation}%, {lightness}%)
          </p>
        </div>
      </div>
    </div>
  )
}
```

Then import and use it:

```mdx
import { ColorGenerator } from "/snippets/color-generator.jsx"

<ColorGenerator />
```

## Considerations

- **SEO**: Search engines may not fully index client-rendered dynamic content.
- **Initial load**: Visitors may see a flash before components render.
- **Accessibility**: Ensure screen readers announce dynamic content changes.
- **Optimize dependency arrays**: Only include necessary dependencies in `useEffect`.
- **Memoize expensive operations**: Use `useMemo` or `useCallback` where appropriate.
- **Reduce re-renders**: Break large components into smaller ones.
- **Lazy loading**: Defer rendering complex components to improve initial page load. Because the MDX sandbox does not support `React.lazy` or dynamic `import()`, gate heavy components behind user interaction or visibility instead. See [Defer rendering for heavy components](https://github.com/#defer-rendering-for-heavy-components).

### Defer rendering for heavy components

`React.lazy`, `Suspense`, and dynamic `import()` are not available in the MDX sandbox. To get the same benefit, render a lightweight placeholder first and only mount the expensive component after the reader opts in. This keeps the initial page load fast while still letting readers interact with the full component.

The example below keeps the `ColorGenerator` from the previous section unmounted until the reader clicks **Load color generator**:

export const LazyColorGenerator = () => { const \[show, setShow\] = useState(false)

if (!show) { return ( <button onClick={() => setShow(true)} className="px-3 py-1.5 text-sm rounded-lg border border-zinc-950/20 dark:border-white/20 text-zinc-950/80 dark:text-white/80" > Load color generator ) }

return }

```mdx
import { ColorGenerator } from "/snippets/color-generator.jsx"

export const LazyColorGenerator = () => {
  const [show, setShow] = useState(false)

  if (!show) {
    return (
      <button onClick={() => setShow(true)}>
        Load color generator
      </button>
    )
  }

  return <ColorGenerator />
}

<LazyColorGenerator />
```

To defer rendering until the component scrolls into view, swap the button for an `IntersectionObserver` set up inside a `useEffect`. The pattern is the same: keep `show` false until the trigger fires, then return the heavy component.