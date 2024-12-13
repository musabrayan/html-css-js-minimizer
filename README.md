# Code Minimizer

A simple and efficient Node.js tool for minifying JavaScript, CSS, and HTML files. This tool reads files from a specified input path and writes their minified versions to a specified output directory, preserving the directory structure.

## Features

- Minifies JavaScript files using [Terser](https://github.com/terser/terser).
- Minifies CSS files using [CSSO](https://github.com/css/csso).
- Minifies HTML files using [html-minifier](https://github.com/kangax/html-minifier).
- Processes individual files or all files in a directory.
- Maintains the input directory structure in the output directory.
- Displays detailed statistics about the minification process.

## Installation

1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```

2. Navigate to the project directory:
   ```bash
   cd code-minimizer
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

## Usage

### Command-line Interface

Run the tool using the following command:

```bash
node index.js -i <input_path> -o <output_path>
```

### Options

- `-i, --input <path>`: Path to the input file or directory (required).
- `-o, --output <path>`: Path to the output directory (required).

### Example

#### Minify a Single File

```bash
node index.js -i ./src/app.js -o ./dist
```

#### Minify All Files in a Directory

```bash
node index.js -i ./src -o ./dist
```

## How It Works

1. The tool identifies the type of each file based on its extension (`.js`, `.css`, `.html`).
2. It applies the appropriate minification process:
   - **JavaScript**: Uses Terser with compression and mangling enabled.
   - **CSS**: Uses CSSO with restructuring.
   - **HTML**: Uses html-minifier with whitespace and comment removal, along with inline minification of JS and CSS.
3. Minified files are written to the output directory, preserving the relative paths of the input files.
4. Displays statistics about the original and minified file sizes and logs any errors encountered.

## Example Output

![image](https://github.com/user-attachments/assets/401f0d9c-d4b0-48e4-9896-61b3ae163b82)


## Error Handling

If an error occurs during file processing, the tool:
- Logs the error to the console.
- Adds the error details to the stats object for inclusion in the final summary.

## Dependencies

- [Terser](https://github.com/terser/terser) for JavaScript minification
- [CSSO](https://github.com/css/csso) for CSS minification
- [html-minifier](https://github.com/kangax/html-minifier) for HTML minification
- [commander](https://github.com/tj/commander.js) for CLI argument parsing

## Contributing

Contributions are welcome! If you find a bug or have a feature request, please open an issue or submit a pull request.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
