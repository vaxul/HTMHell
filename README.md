# HTMHell - Markup From Hell

A collection of bad practices in HTML, copied from real websites.
## Contributing

### Rules

* Please only contribute examples you copy from production websites.  
* Remove attributes that don't add any value.
* Remove any pointers that show where you've copied the code. We don't want to blame anyone.
* Only copy code from *modern* websites.

### Basics

1. Fork this repo and install the dependencies.
  ```
  npm install
  ```

2. Run the project
  ```
  npm run start
  ```

3. Create a pull request.


### Adding authors

Add an author in `./hell/_data/authors.js` if they're not listed.

```
{
  "id": "UNIQUE ID",
  "name": "DISPLAY NAME",
  "link": "WEBSITE/TWITTER/GITHUB"
}
```

### Adding a submission

Add a submission in `./hell/entries` by copying any other markdown file in this folder. The filename should start with a counter followed by any file name, e.g. `12_my_entry.md`.

1. Show bad code
2. Explain how to fix it
3. Show good code
