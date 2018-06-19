## 01_quickstart

1. Set up the Development Environment
  - `node -v` 8.x or higher
  - `npm -v`  5.x or higher
  
2. Install the Angular CLI globally

  ``` node
  npm install -g @angular/cli
  ```

3. Create a new project

  ```node
  ng new my-app
  ```
  
  ---
  ERROR
  ---
  `Error [ERR_STREAM_WRITE_AFTER_END]: write after end`
  
  -  `sudo npm install -g npm@latest`
  -  `npm cache verify`
  ---

4. Run demo

```
cd my-app
ng serve --open
```

- `ng serve`: watches your files, rebuilds when saving
- `--open` will open the browser

5. Play around 

- `ng test`, `npm test` also works
- 'src/browserslist' is for browswer supports
- 'karma.conf.js' is for testing
- 'main.ts', is **JIT** by default, good for dev. However, `ng build --aot` will run **AOT**, which is perfect for production.


