## Hello, World!

Now that you’ve installed Rust, it’s time to write your first Rust program.
It’s traditional when learning a new language to write a little program that
prints the text `Hello, world!` to the screen, so we’ll do the same here!

> Note: This book assumes basic familiarity with the command line. Rust makes
> no specific demands about your editing or tooling or where your code lives, so
> if you prefer to use an integrated development environment (IDE) instead of
> the command line, feel free to use your favorite IDE. Many IDEs now have some
> degree of Rust support; check the IDE’s documentation for details. The Rust
> team has been focusing on enabling great IDE support via `rust-analyzer`. See
> [Appendix D][devtools]<!-- ignore --> for more details.

### Creating a Project Directory

You’ll start by making a directory to store your Rust code. It doesn’t matter
to Rust where your code lives, but for the exercises and projects in this book,
we suggest making a _projects_ directory in your home directory and keeping all
your projects there.

Open a terminal and enter the following commands to make a _projects_ directory
and a directory for the “Hello, world!” project within the _projects_ directory.

For Linux, macOS, and PowerShell on Windows, enter this:

```console
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

For Windows CMD, enter this:

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

### Writing and Running a Rust Program

Next, make a new source file and call it _main.rs_. Rust files always end with
the _.rs_ extension. If you’re using more than one word in your filename, the
convention is to use an underscore to separate them. For example, use
_hello_world.rs_ rather than _helloworld.rs_.

Now open the _main.rs_ file you just created and enter the code in Listing 1-1.

<Listing number="1-1" file-name="main.rs" caption="A program that prints `Hello, world!`">

```rust
fn main() {
    println!("Hello, world!");
}
```

</Listing>

Save the file and go back to your terminal window in the
_~/projects/hello_world_ directory. On Linux or macOS, enter the following
commands to compile and run the file:

```console
$ rustc main.rs
$ ./main
Hello, world!
```

On Windows, enter the command `.\main` instead of `./main`:

```powershell
> rustc main.rs
> .\main
Hello, world!
```

Regardless of your operating system, the string `Hello, world!` should print to
the terminal. If you don’t see this output, refer back to the
[“Troubleshooting”][troubleshooting]<!-- ignore --> part of the Installation
section for ways to get help.

If `Hello, world!` did print, congratulations! You’ve officially written a Rust
program. That makes you a Rust programmer—welcome!

### Anatomy of a Rust Program

Let’s review this “Hello, world!” program in detail. Here’s the first piece of
the puzzle:

```rust
fn main() {

}
```

These lines define a function named `main`. The `main` function is special: it
is always the first code that runs in every executable Rust program. Here, the
first line declares a function named `main` that has no parameters and returns
nothing. If there were parameters, they would go inside the parentheses `()`.

The function body is wrapped in `{}`. Rust requires curly brackets around all
function bodies. It’s good style to place the opening curly bracket on the same
line as the function declaration, adding one space in between.

> Note: If you want to stick to a standard style across Rust projects, you can
> use an automatic formatter tool called `rustfmt` to format your code in a
> particular style (more on `rustfmt` in
> [Appendix D][devtools]<!-- ignore -->). The Rust team has included this tool
> with the standard Rust distribution, as `rustc` is, so it should already be
> installed on your computer!

The body of the `main` function holds the following code:

```rust
println!("Hello, world!");
```

This line does all the work in this little program: it prints text to the
screen. There are three important details to notice here.

First, `println!` calls a Rust macro. If it had called a function instead, it
would be entered as `println` (without the `!`). Rust macros are a way to write
code that generates code to extend Rust syntax, and we’ll discuss them in more
detail in [Chapter 20][ch20-macros]<!-- ignore -->. For now, you just need to
know that using a `!` means that you’re calling a macro instead of a normal
function and that macros don’t always follow the same rules as functions.

Second, you see the `"Hello, world!"` string. We pass this string as an argument
to `println!`, and the string is printed to the screen.

Third, we end the line with a semicolon (`;`), which indicates that this
expression is over and the next one is ready to begin. Most lines of Rust code
end with a semicolon.

### Compiling and Running Are Separate Steps

You’ve just run a newly created program, so let’s examine each step in the
process.

Before running a Rust program, you must compile it using the Rust compiler by
entering the `rustc` command and passing it the name of your source file, like
this:

```console
$ rustc main.rs
```

If you have a C or C++ background, you’ll notice that this is similar to `gcc`
or `clang`. After compiling successfully, Rust outputs a binary executable.

On Linux, macOS, and PowerShell on Windows, you can see the executable by
entering the `ls` command in your shell:

```console
$ ls
main  main.rs
```

On Linux and macOS, you’ll see two files. With PowerShell on Windows, you’ll
see the same three files that you would see using CMD. With CMD on Windows, you
would enter the following:

```cmd
> dir /B %= the /B option says to only show the file names =%
main.exe
main.pdb
main.rs
```

This shows the source code file with the _.rs_ extension, the executable file
(_main.exe_ on Windows, but _main_ on all other platforms), and, when using
Windows, a file containing debugging information with the _.pdb_ extension.
From here, you run the _main_ or _main.exe_ file, like this:

```console
$ ./main # or .\main on Windows
```

If your _main.rs_ is your “Hello, world!” program, this line prints `Hello,
world!` to your terminal.

If you’re more familiar with a dynamic language, such as Ruby, Python, or
JavaScript, you might not be used to compiling and running a program as
separate steps. Rust is an _ahead-of-time compiled_ language, meaning you can
compile a program and give the executable to someone else, and they can run it
even without having Rust installed. If you give someone a _.rb_, _.py_, or
_.js_ file, they need to have a Ruby, Python, or JavaScript implementation
installed (respectively). But in those languages, you only need one command to
compile and run your program. Everything is a trade-off in language design.

Just compiling with `rustc` is fine for simple programs, but as your project
grows, you’ll want to manage all the options and make it easy to share your
code. Next, we’ll introduce you to the Cargo tool, which will help you write
real-world Rust programs.

{{#quiz ../quizzes/ch01-02-hello-world.toml}}


[troubleshooting]: ch01-01-installation.html#troubleshooting
[devtools]: appendix-04-useful-development-tools.html
[ch20-macros]: ch20-05-macros.html
