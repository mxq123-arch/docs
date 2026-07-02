# Source: https://github.com/mintlify/docs/blob/main/create/reusable-snippets.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# reusable-snippets.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/create/reusable-snippets.mdx)

History

171 lines (114 loc) · 5.26 KB

## FilesExpand file tree

 main

/

# reusable-snippets.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

171 lines (114 loc) · 5.26 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/reusable-snippets.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Reusable snippets</td></tr><tr><th>description</th><td>Create reusable content snippets with variables to maintain consistency across documentation pages and reduce duplication in your MDX files.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">content snippets</div></th><th><div dir="auto">reusable content</div></th><th><div dir="auto">variables</div></th></tr></tbody></table></td></tr></tbody></table>

One of the core principles of software development is DRY (Don't Repeat Yourself), which applies to documentation too. If you find yourself repeating the same content in multiple places, create a custom snippet for that content. Snippets contain content that you can import into other files to reuse. You control where the snippet appears on a page. If you ever need to update the content, you only need to edit the snippet rather than every file where the snippet is used.

Snippets are not currently supported in the web editor. To use snippets, edit your MDX files locally with the CLI or push snippet imports directly to your repository.

## How snippets work

Snippets are any `.mdx`, `.md`, or `.jsx` files imported into another file. You can place snippet files anywhere in your project.

When you import a snippet into another file, the snippet only appears where you import it and does not render as a standalone page. Any file in the `/snippets/` folder is always a snippet even if it is not imported into another file.

## Create snippets

Create a file with the content you want to reuse. Snippets can contain all content types supported by Mintlify and they can import other snippets.

## Import snippets into pages

Import snippets into pages using either an absolute or relative path.

- **Absolute imports**: Start with `/` for imports from the root of your project.
- **Relative imports**: Use `./` or `../` to import snippets relative to the current file's location.

Relative imports enable IDE navigation. Press CMD and click a snippet name in your editor to jump directly to the snippet definition.

### Import text

1. Add content to your snippet file that you want to reuse.
 
 ```mdx
    Hello world! This is my content I want to reuse across pages.
    ```
 
2. Import the snippet into your destination file using either an absolute or relative path.
 
 ```mdx
    ---
    title: "An example page"
    description: "This is an example page that imports a snippet."
    ---
    
    import MySnippet from "/shared/my-snippet.mdx";
    
    The snippet content displays beneath this sentence.
    
    <MySnippet />
    ```
 
 ```mdx
    ---
    title: "An example page"
    description: "This is an example page that imports a snippet."
    ---
    
    import MySnippet from "../shared/my-snippet.mdx";
    
    The snippet content displays beneath this sentence.
    
    <MySnippet />
    ```
 

### Import variables

Reference variables from a snippet in a page.

1. Export variables from a snippet file.
 
 ```mdx
    export const myName = "Ronan";
    
    export const myObject = { fruit: "strawberries" };
    
    ;
    ```
 
2. Import the snippet from your destination file and use the variable.
 
 ```mdx
    ---
    title: "An example page"
    description: "This is an example page that imports a snippet with variables."
    ---
    
    import { myName, myObject } from "/shared/custom-variables.mdx";
    
    Hello, my name is {myName} and I like {myObject.fruit}.
    ```
 

### Import snippets with variables

Use variables to pass data to a snippet when you import it.

1. Add variables to your snippet and pass in properties when you import it. In this example, the variable is `{word}`.
 
 ```mdx
    My keyword of the day is {word}.
    ```
 
2. Import the snippet into your destination file with the variable. The passed property replaces the variable in the snippet definition.
 
 ```mdx
    ---
    title: "An example page"
    description: "This is an example page that imports a snippet with a variable."
    ---
    
    import MySnippet from "/shared/my-snippet.mdx";
    
    <MySnippet word="bananas" />
    ```
 

Variables also interpolate inside fenced code blocks. This is useful for snippets that include installation commands or other code examples that differ by package name, version, or environment.

```mdx
export const InstallSnippet = ({ packageName }) => <></>;

Install the package:

```bash
npm install {packageName}
```
```

```mdx
import InstallSnippet from "/shared/install-snippet.mdx";

<InstallSnippet packageName="@myorg/sdk" />
```

### Import React components

1. Create a snippet with a JSX component. See [React components](https://github.com/mintlify/docs/blob/main/customize/react-components) for more information.
 
 ```js
    export const MyJSXSnippet = () => {
      return (
        <div>
          <h1>Hello, world!</h1>
        </div>
      );
    };
    ```
 

When creating JSX snippets, use arrow function syntax (\`=>\`) rather than function declarations. The \`function\` keyword is not supported in snippets.

2. Import the snippet.
 
 ```mdx
    ---
    title: "An example page"
    description: "This is an example page that imports a snippet with a React component."
    ---
    
    import { MyJSXSnippet } from "/components/my-jsx-snippet.jsx";
    
    <MyJSXSnippet />
    ```