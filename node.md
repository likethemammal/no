
### __dirname vs __filename vs process.cwd()

__dirname will return just `/` when referencing the current dir.

__filename is just the name of the file. You can use path.basename to easily get the filename without the extension

### node fetch vs fs.readFileSync

fetch() in node needs an absolute path. Even using the path module and path.resolve doesnt fix the issue. fetch() does work with files inside the current directory.

#### Next and _app.js

Next doesnt allow page to use the fs module unless it is used in getStaticProps or getServerSideProps ([comment][github_reference_next_app])

[github_reference_next_app]: https://github.com/vercel/next.js/issues/7755#issuecomment-624544303
