# Linting

Linting is process of analyzing code for potential errors, bugs and stylistic issues.
It provides many benefits including:

- Consistent code style
- Improved code quality
- Catch common mistakes early in development

Two common linting tools in modern javascript development are `ESLint` and `Prettier`. These too tools are very similar, yet slightly different.

# ESLint

> **ESLint**
>
> ESLint is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code, with the goal of making code more consistent and avoiding bugs.

**1. Focus:**
ESLint focuses on code quality and enforcing coding standards. It helps developers catch and fix issues related to the correctness and quality of the JavaScript code.

**2. What It Checks:**
ESLint checks for:

- syntax errors
- coding style violations
- potential bugs
- best practices adherence

**3. Customization:**
ESLint is highly customizable. Developers can easily configure its rules according to the requirements through `.eslintrc`.

**4. Integration:**
ESLint can be integrated into your development environment and build tools to perform static code analysis and provide feedback during development. It works seamlessly with code editors, build systems, and continuous integration pipelines.

**5. Error Messages:**
ESLint provides detailed error messages that help developers understand the nature of the issues in the code, making it easier to pinpoint and fix problems.

# Prettier

> **Prettier**
>
> Prettier enforces a consistent code style (i.e. code formatting that won’t affect the AST _Abstract Syntax Tree_) across your entire codebase because it disregards the original styling by parsing it away and re-printing the parsed AST with its own rules that take the maximum line length into account, wrapping code when necessary.

**1. Focus:**
Prettier's primary focus is on code formatting. It ensures that your code is consistently styled and visually appealing without delving into the correctness or quality of the code logic.

**2. What It Checks:**
Prettier checks and automatically enforces a strict set of formatting rules on your code. It adjusts aspects like indentation, line breaks, and spacing to maintain a uniform visual style.

**3. Customization:**
Prettier is opinionated and does not provide extensive customization options. It enforces its formatting rules without allowing you to configure individual rules or create custom formatting rules.

**4. Integration:**
Prettier integrates into code editors and build pipelines to automatically format code when you save a file or run a command. It doesn't provide detailed code analysis but ensures that your code looks consistent.

**5. Error Messages:**
Prettier does not provide error messages related to code quality or coding standards. It's solely concerned with code formatting and does not offer feedback on issues like potential bugs or best practices violations.

> In summary, ESLint is a tool for maintaining **code quality and enforcing coding standards** and Prettier is focused solely on **code formatting**

# Configuration

#### Requirements

Node.js (^12.22.0, ^14.17.0, or >=16.0.0) with SSL support

## Steps

1. Install `eslint` and `prettier` to the project as dev dependency

```
npm install --save-dev eslint prettier
OR
yarn add -D eslint prettier
```

2. Add `.eslintrc*` file

```
touch .eslintrc.js
OR
touch .eslintrc.json
```

3. [Optional] create `.prettierrc`, `.prettierignore` and `.eslintignore`

   > Tip! Base your .prettierignore on .gitignore and .eslintignore (if you have one).

4. Add eslint configuration to the `.eslintrc*` file.

   > For more information, refer to eslint documentation [documentation](https://eslint.org/docs/latest/use/configure/)

5. [Optional] If you are using VS Code, you can add eslint and prettier extension for better development experience.

   - [eslint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
   - [prettier extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

6. [Optional] If you are using VS Code, you can add auto format and auto lint to the settings.

```
.vscode/settings.json

{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.addMissingImports": true
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```
