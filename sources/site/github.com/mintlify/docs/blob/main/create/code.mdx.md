# Source: https://github.com/mintlify/docs/blob/main/create/code.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# code.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/create/code.mdx)

History

573 lines (432 loc) · 14.5 KB

## FilesExpand file tree

 main

/

# code.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

573 lines (432 loc) · 14.5 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/code.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Format code</td></tr><tr><th>description</th><td>Format code in your documentation with syntax highlighting, line numbers, diffs, copy buttons, and interactive code group features in MDX.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">code blocks</div></th><th><div dir="auto">syntax highlighting</div></th><th><div dir="auto">code styling</div></th></tr></tbody></table></td></tr></tbody></table>

## Add code samples

You can add inline code snippets or code blocks. Code blocks support meta options for syntax highlighting, titles, line highlighting, icons, and more.

### Inline code

To denote a `word` or `phrase` as code, enclose it in backticks (\`).

```mdx
To denote a `word` or `phrase` as code, enclose it in backticks (`).
```

### Code blocks

Use [fenced code blocks](https://www.markdownguide.org/extended-syntax/#fenced-code-blocks) by enclosing code in three backticks. Code blocks are copyable, and if you have the assistant enabled, users can ask the assistant to explain the code.

Specify the programming language for syntax highlighting and to enable meta options. Add any meta options, like a title or icon, after the language.

```java
class HelloWorld {
 public static void main(String[] args) {
 System.out.println("Hello, World!");
 }
}
```

```mdx
```java HelloWorld.java example lines icon="java"
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
```

## Code block options

Add meta options to your code blocks to customize their appearance.

You must specify a programming language for a code block before adding any other meta options.

### Option syntax

-   **String and boolean options**: Wrap with `""`, `''`, or no quotes.
-   **Expression options**: Wrap with `{}`, `""`, or `''`.

### Syntax highlighting

Enable syntax highlighting by specifying the programming language after the opening backticks of a code block.

Mintlify uses [Shiki](https://shiki.style/) for syntax highlighting and supports all available languages. See the full list of [languages](https://shiki.style/languages) in Shiki's documentation.

Customize code block themes globally using `styling.codeblocks` in your `docs.json` file. Set simple themes like `system` or `dark`, or configure custom [Shiki themes](https://shiki.style/themes) for light and dark modes. See [Settings](https://github.com/mintlify/docs/blob/main/organize/settings-appearance#styling) for configuration options.

```java
class HelloWorld {
 public static void main(String[] args) {
 System.out.println("Hello, World!");
 }
}
```

```mdx
```java Syntax highlighting example
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
```

For custom themes, set your theme in \`docs.json\` to \`"css-variables"\` and override syntax highlighting colors using CSS variables with the \`--mint-\` prefix.

The following variables are available:

**Basic colors**

-   `--mint-color-text`: Default text color
-   `--mint-color-background`: Background color

**Token colors**

-   `--mint-token-constant`: Constants and literals
-   `--mint-token-string`: String values
-   `--mint-token-comment`: Comments
-   `--mint-token-keyword`: Keywords
-   `--mint-token-parameter`: Function parameters
-   `--mint-token-function`: Function names
-   `--mint-token-string-expression`: String expressions
-   `--mint-token-punctuation`: Punctuation marks
-   `--mint-token-link`: Links

**ANSI colors**

-   `--mint-ansi-black`, `--mint-ansi-black-dim`
-   `--mint-ansi-red`, `--mint-ansi-red-dim`
-   `--mint-ansi-green`, `--mint-ansi-green-dim`
-   `--mint-ansi-yellow`, `--mint-ansi-yellow-dim`
-   `--mint-ansi-blue`, `--mint-ansi-blue-dim`
-   `--mint-ansi-magenta`, `--mint-ansi-magenta-dim`
-   `--mint-ansi-cyan`, `--mint-ansi-cyan-dim`
-   `--mint-ansi-white`, `--mint-ansi-white-dim`
-   `--mint-ansi-bright-black`, `--mint-ansi-bright-black-dim`
-   `--mint-ansi-bright-red`, `--mint-ansi-bright-red-dim`
-   `--mint-ansi-bright-green`, `--mint-ansi-bright-green-dim`
-   `--mint-ansi-bright-yellow`, `--mint-ansi-bright-yellow-dim`
-   `--mint-ansi-bright-blue`, `--mint-ansi-bright-blue-dim`
-   `--mint-ansi-bright-magenta`, `--mint-ansi-bright-magenta-dim`
-   `--mint-ansi-bright-cyan`, `--mint-ansi-bright-cyan-dim`
-   `--mint-ansi-bright-white`, `--mint-ansi-bright-white-dim`

**Custom syntax highlighting**

Add syntax highlighting for languages not included in Shiki's default set by providing custom TextMate grammar files. Create a JSON file following the [TextMate grammar format](https://macromates.com/manual/en/language_grammars), then reference it in your `docs.json`. You can add multiple custom languages by including additional paths in the array.

```json
{
 "styling": {
 "codeblocks": {
 "languages": {
 "custom": ["/languages/my-custom-language.json"]
 }
 }
 }
}
```

### Twoslash

In JavaScript and TypeScript code blocks, use `twoslash` to enable interactive type information. Users can hover over variables, functions, and parameters to see types and errors like in an IDE.

```ts
type Pet = "cat" | "dog" | "hamster";

function adoptPet(name: string, type: Pet) {
 return `${name} the ${type} is now adopted!`;
}

// Hover to see the inferred types
const message = adoptPet("Mintie", "cat");
```

```mdx
```ts twoslash Twoslash example
type Pet = "cat" | "dog" | "hamster";

function adoptPet(name: string, type: Pet) {
  return `${name} the ${type} is now adopted!`;
}

// Hover to see the inferred types
const message = adoptPet("Mintie", "cat");
```
```

### Title

Add a title to label your code example. Place the title after the language identifier. Titles can contain multiple words and file paths.

You can set the title two ways:

-   **Inline**: Place the title directly after the language identifier.
-   **`title` property**: Use `title="Your title"` for titles that need special characters or explicit quoting.

```js
const hello = "world";
```

```js
const hello = "world";
```

```mdx
```javascript Example title
const hello = "world";
```
```

```mdx
```javascript title="utils/hello.js"
const hello = "world";
```
```

### Icon

Add an icon to your code block using the `icon` property. See [Icons](https://github.com/mintlify/docs/blob/main/components/icons) for all available options.

```js
const hello = "world";
```

```mdx
```javascript Icon example icon="square-js"
const hello = "world";
```
```

### Line highlighting

Highlight specific lines in your code blocks using `highlight` with the line numbers or ranges you want to highlight.

```js
const greeting = "Hello, World!";
function sayHello() {
 console.log(greeting);
}
sayHello();
```

```mdx
```javascript Line highlighting example highlight={1-2,5}
const greeting = "Hello, World!";
function sayHello() {
  console.log(greeting);
}
sayHello();
```
```

### Line focusing

Focus on specific lines in your code blocks using `focus` with line numbers or ranges.

```js
const greeting = "Hello, World!";
function sayHello() {
 console.log(greeting);
}
sayHello();
```

```mdx
```javascript Line focusing example focus={2,4-5}
const greeting = "Hello, World!";
function sayHello() {
  console.log(greeting);
}
sayHello();
```
```

### Show line numbers

Display line numbers on the left side of your code block using `lines`.

```js
const greeting = "Hello, World!";
function sayHello() {
 console.log(greeting);
}
sayHello();
```

```mdx
```javascript Show line numbers example lines
const greeting = "Hello, World!";
function sayHello() {
  console.log(greeting);
}
sayHello();
```
```

### Expandable

Allow users to expand and collapse long code blocks using `expandable`.

```python
from datetime import datetime, timedelta
from typing import Dict, List, Optional
from dataclasses import dataclass

@dataclass
class Book:
title: str
author: str
isbn: str
checked_out: bool = False
due_date: Optional[datetime] = None

class Library:
 def __init__(self):
 self.books: Dict[str, Book] = {}
 self.checkouts: Dict[str, List[str]] = {} # patron -> list of ISBNs

 def add_book(self, book: Book) -> None:
 if book.isbn in self.books:
 raise ValueError(f"Book with ISBN {book.isbn} already exists")
 self.books[book.isbn] = book

 def checkout_book(self, isbn: str, patron: str, days: int = 14) -> None:
 if patron not in self.checkouts:
 self.checkouts[patron] = []

 book = self.books.get(isbn)
 if not book:
 raise ValueError("Book not found")

 if book.checked_out:
 raise ValueError("Book is already checked out")

 if len(self.checkouts[patron]) >= 3:
 raise ValueError("Patron has reached checkout limit")

 book.checked_out = True
 book.due_date = datetime.now() + timedelta(days=days)
 self.checkouts[patron].append(isbn)

 def return_book(self, isbn: str) -> float:
 book = self.books.get(isbn)
 if not book or not book.checked_out:
 raise ValueError("Book not found or not checked out")

 late_fee = 0.0
 if datetime.now() > book.due_date:
 days_late = (datetime.now() - book.due_date).days
 late_fee = days_late * 0.50

 book.checked_out = False
 book.due_date = None

 # Remove from patron's checkouts
 for patron, books in self.checkouts.items():
 if isbn in books:
 books.remove(isbn)
 break

 return late_fee

 def search(self, query: str) -> List[Book]:
 query = query.lower()
 return [
 book for book in self.books.values()
 if query in book.title.lower() or query in book.author.lower()
 ]

def main():
 library = Library()

 # Add some books
 books = [
 Book("The Hobbit", "J.R.R. Tolkien", "978-0-261-10295-4"),
 Book("1984", "George Orwell", "978-0-452-28423-4"),
 ]

 for book in books:
 library.add_book(book)

 # Checkout and return example
 library.checkout_book("978-0-261-10295-4", "patron123")
 late_fee = library.return_book("978-0-261-10295-4")
 print(f"Late fee: ${late_fee:.2f}")

if __name__ == "__main__":
 main()
```

````
```python Expandable example expandable
from datetime import datetime, timedelta
from typing import Dict, List, Optional
from dataclasses import dataclass

# ...

if __name__ == "__main__":
    main()
```
````

### Wrap

Enable text wrapping for long lines using `wrap`. This prevents horizontal scrolling and makes long lines easier to read.

```js
const greeting =
 "Hello, World! I am a long line of text that will wrap to the next line.";
function sayHello() {
 console.log(greeting);
}
sayHello();
```

```mdx
```javascript Wrap example wrap
const greeting =
  "Hello, World! I am a long line of text that will wrap to the next line.";
function sayHello() {
  console.log(greeting);
}
sayHello();
```
```

### Diff

Show a visual diff of added or removed lines in your code blocks. Added lines are highlighted in green and removed lines are highlighted in red.

Add `[!code ++]` or `[!code --]` inside a comment at the end of a line to mark it as added or removed. Use your language's comment syntax:

| Language | Added | Removed |
| --- | --- | --- |
| JavaScript, TypeScript, Java, C, C++, Go, Rust | `// [!code ++]` | `// [!code --]` |
| Python, Ruby, Bash, YAML | `# [!code ++]` | `# [!code --]` |
| HTML, XML | `<!-- [!code ++] -->` | `<!-- [!code --] -->` |
| CSS | `/* [!code ++] */` | `/* [!code --] */` |
| SQL, Lua | `-- [!code ++]` | `-- [!code --]` |

For multiple consecutive lines, add a colon and the number of lines:

-   `// [!code ++:3]`: Mark the current line plus the next two lines as added.
-   `# [!code --:5]`: Mark the current line plus the next four lines as removed.

```js
const greeting = "Hello, World!"; // [!code ++]
function sayHello() {
 console.log("Hello, World!"); // [!code --]
 console.log(greeting); // [!code ++]
}
sayHello();
```

```python
def greet():
 print("Hello, World!") # [!code --]
 print("Hello, Mintlify!") # [!code ++]

greet()
```

````
```js JavaScript diff lines
const greeting = "Hello, World!"; // [!code ++]
function sayHello() {
  console.log("Hello, World!"); // [!code --]
  console.log(greeting); // [!code ++]
}
sayHello();
```
````

````
```python Python diff lines
def greet():
    print("Hello, World!")  # [!code --]
    print("Hello, Mintlify!")  # [!code ++]

greet()
```
````

## CodeBlock component

Use the `<CodeBlock>` component in custom React components to programmatically render code blocks with the same styling and features as markdown code blocks.

### Props

The programming language for syntax highlighting. The filename to display in the code block header. The icon to display in the code block header. See \[Icons\](/components/icons) for available options. Whether to show line numbers. Whether to wrap the code block. Whether to expand the code block. The lines to highlight. Provide a stringified array of numbers. Example: \`"\[1,3,4,5\]"\`. The lines to focus on. Provide a stringified array of numbers. Example: \`"\[1,3,4,5\]"\`.

### Example

```js
export const CustomCodeBlock = ({
 filename,
 icon,
 language,
 highlight,
 children,
}) => {
 return (
 <CodeBlock
 filename={filename}
 icon={icon}
 language={language}
 lines
 highlight={highlight}
 >
 {children}
 </CodeBlock>
 );
};
```