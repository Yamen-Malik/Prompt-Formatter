# Prompt Formatter

This command line tool helps you change the appearance of your command line prompt and store your favorite formats to use them at any time.

## Usage

```bash
prompt-formatter <command> [options]
```

### Commands

- `set <format>`: Set the prompt to the given format.
- `store`: Store the current format.
- `set-default [<index>]`: Set the the preferred default format to the current or the specified format.
- `load <index>`: Set the prompt to the saved format at the given index.
- `reset`: Set the prompt to the default format.
- `default`: Set the prompt to the preferred default format.
- `random`: Set the prompt to a random format.
- `view <index>`: Print the stored format at the given index.
- `ls (or list)`: List all of the stored formats.
- `del (or delete) <index>`: Delete the stored format at the given index.
- `help (-h or --help)`: Display the help message.

## Getting Started

1. Clone this repository to your local machine.

2. Navigate to the repository's directory:
   ```bash
   cd /path/to/prompt-formatter
   ```

3. Make the script executable:
   ```bash
   chmod +x prompt-formatter
   ```

4. Use the script as described in the <a href="#usage">Usage</a> section above.

## Using the `set` Command

The `set` command allows you to customize your prompt format by specifying various options. You can format your prompt string by using color options and additional options to display user information, the current working directory, time, date, and more.

### Color Options

The script supports the following colors that you can use in your prompt format:

- `black`
- `orange`
- `cyan`
- `lightRed`
- `lightBlue`
- `white`
- `red`
- `blue`
- `lightGray`
- `lightGreen`
- `lightPurple`
- `reset` (which resets the color to the default)

To use color options, simply include them in your format string using a `-` followed by the color name.

#### Example:

```bash
prompt-formatter set -blue '$' -green '>' -reset
```

### Other Options

You can also include various other options in your prompt format:

- `u`: Display the user name.
- `h`: Display the hostname.
- `w`: Display the path to the working directory.
- `W`: Display the working directory name.
- `t`: Display the time.
- `d`: Display the date.
- `n`: Add a newline.
- `s`: Add a space.

To use these options, include them in your format string using a `-` followed by the option. You can combine multiple options in your format string as needed.

#### Example

```bash
prompt-formatter set -green -u @ -h / -W : -s -orange
```

Experiment with different color and option combinations to create a custom prompt format that suits your preferences.

> Don't forget to use `prompt-formatter store` to save the format you set.


## Adding an Alias

To make it even easier to use the "prompt-formatter" tool, you can add an alias to your `.bashrc` file.

1. Open your `.bashrc` file using a text editor:
   ```bash
   nano ~/.bashrc
   ```

2. Add the following line at the end of the file:
   ```bash
   alias custom-prompt='. path/to/prompt-formatter'
   ```

3. To apply the changes immediately, either run the following command or restart your terminal:
   ```bash
   source ~/.bashrc
   ```

Now you can use the "prompt-formatter" tool by simply typing `custom-prompt` in your terminal.

## Automatically Loading Preferred Format

You can configure your `custom-prompt` alias to automatically load your preferred format when your terminal starts by adding an option to your `.bashrc` file.

### Loading the Default Format

To load the default format automatically, add the following line to your `.bashrc` file:

```bash
custom-prompt default
```

### Loading a Random Format

If you want to load a random format from the stored formats each time you start your terminal, add the following line to your `.bashrc` file:

```bash
custom-prompt random
```

Remember to make sure that the `custom-prompt` alias is defined as explained in the <a href="#adding-an-alias">Adding an Alias</a> section above.

After making these changes and saving the file, the specified format will be applied automatically when you start a new terminal session.
