# angular-create-angular-plugin-for-npm

Creating an Angular library that can be published as an npm package allows you to share reusable code and components with the Angular community. Here's a step-by-step guide on how to create an Angular library and publish it to npm:

### Step 1: Set Up Your Angular Library

1. **Create a New Angular Workspace:**

   If you don't already have an Angular workspace, you can create one using the Angular CLI. Run the following command to create a new workspace:

   ```bash
   ng new my-angular-library
   ```

2. **Create a Library:**

   Inside your Angular workspace, create a library using the Angular CLI. Replace `my-library` with your library name:

   ```bash
   ng generate library my-library
   ```

   This command will generate a new library project under the `projects` folder of your workspace.

### Step 2: Write Your Angular Code

1. **Develop Your Library:**

   Write your Angular components, services, and modules within the library project (`projects/my-library/src/lib`). You can create reusable Angular components, directives, and services in this project.

2. **Export Components and Services:**

   Make sure to export the components and services that you want to expose to users of your library. In each component or service file, add `export` statements to make them accessible.

### Step 3: Build Your Library

1. **Build the Library:**

   To build your Angular library, run the following command from your library project directory (`projects/my-library`):

   ```bash
   ng build my-library
   ```

   This will compile your library into a distributable format in the `dist` folder.

### Step 4: Create an npm Package

1. **Prepare the npm Package:**

   Navigate to the `dist/my-library` directory, which contains your compiled library. Run the following command to create an npm package:

   ```bash
   cd dist/my-library
   npm pack
   ```

   This will create a `.tgz` (tarball) file containing your library, which can be published to npm.

### Step 5: Publish Your Library to npm

1. **Create an npm Account:**

   If you don't have an npm account, you can sign up at [npmjs.com](https://www.npmjs.com/signup).

2. **Log In:**

   In your terminal, run the following command to log in to npm using your credentials:

   ```bash
   npm login
   ```

3. **Publish Your Package:**

   Run the following command to publish your library to the npm registry:

   ```bash
   npm publish my-library-1.0.0.tgz
   ```

   Replace `my-library-1.0.0.tgz` with the actual filename of your library tarball. The version number should match the version specified in your library's `package.json` file.

### Step 6: Using Your Published Angular Library

To use your published Angular library in another Angular project:

1. In the target Angular project, navigate to the project directory in your terminal.

2. Run the following command to install your library from npm:

   ```bash
   npm install my-library
   ```

3. Import and use the components and services from your library in your Angular application code.

   ```typescript
   import { Component } from '@angular/core';
   import { MyLibraryService } from 'my-library';

   @Component({
     selector: 'app-root',
     template: `
       <h1>Using My Angular Library</h1>
       <p>{{ libraryService.getMessage() }}</p>
     `,
   })
   export class AppComponent {
     constructor(private libraryService: MyLibraryService) {}
   }
   ```

That's it! You've successfully created an Angular library and published it to npm. Users can now install and use your library in their Angular applications.
