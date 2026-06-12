To create a blank TypeScript project from scratch, you need to initialize a Node.js project, install the TypeScript compiler, and configure your build settings.Here is the fastest step-by-step setup using your terminal:1. Initialize and InstallCreate a new project folder, initialize a package.json file, and install TypeScript as a development dependency.


bashmkdir my-ts-project-01
cd my-ts-project-01
npm init -y
npm install typescript @types/node --save-dev


Use code with caution.2. Generate the Configuration FileGenerate the tsconfig.json file, which tells the compiler how to transpile your TypeScript code into standard JavaScript.

bashnpx tsc --init

Use code with caution.3. Configure tsconfig.jsonOpen the newly created tsconfig.json file and ensure the following core settings are uncommented and configured to separate your source files from your build output:


json

{
  "compilerOptions": {
    "target": "ES2022",                          // Target modern JavaScript
    "module": "NodeNext",                        // Modern module system
    "moduleResolution": "NodeNext",
    "outDir": "./dist",                          // Where compiled JS files go
    "rootDir": "./src",                          // Where your TS source files live
    "strict": true,                              // Enable all strict type-checking
    "esModuleInterop": true                      // Fixes compatibility imports
  }
}

Use code with caution.4. Create Source CodeCreate a src directory and add your first TypeScript file.

bash

mkdir src
echo "const message: string = 'Hello, TypeScript!';" > src/index.ts
echo "console.log(message);" >> src/index.ts


Use code with caution.5. Build and RunAdd convenience scripts to your package.json file to easily compile and run your code.

json

"scripts": {
  "build": "tsc",
  "start": "node dist/index.js"
}
Use code with caution.Now, compile your project and run the output by executing:

bash

npm run build
npm start