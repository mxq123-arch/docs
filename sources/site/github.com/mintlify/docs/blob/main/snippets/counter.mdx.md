# Source: https://github.com/mintlify/docs/blob/main/snippets/counter.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# counter.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![handotdev](https://avatars.githubusercontent.com/u/44352119?v=4&size=40)](https://github.com/handotdev) [handotdev](https://github.com/mintlify/docs/commits?author=handotdev)

[Update react components docs](https://github.com/mintlify/docs/commit/db1c6de9048ae46f412cf4da2abde4875a4848cf)

success

Apr 28, 2025

[db1c6de](https://github.com/mintlify/docs/commit/db1c6de9048ae46f412cf4da2abde4875a4848cf) · Apr 28, 2025

## History

[History](https://github.com/mintlify/docs/commits/main/snippets/counter.mdx)

Open commit details

History

32 lines (28 loc) · 1.06 KB

## FilesExpand file tree

 main

/

# counter.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

32 lines (28 loc) · 1.06 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/snippets/counter.mdx)

Copy raw file

Download raw file

Edit and raw actions

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