# Load html templates in div's that have their template attributes set

<img src="https://github.com/madeinouweland/html-template-loading/blob/master/template.png" width="400" />

```
[... body.childNodes]
  .filter(x => x.attributes !== undefined)
  .filter(x => x.attributes.getNamedItem('template') !== null)
  .map(x => {
    fetch(`${x.attributes.getNamedItem('template').value}.html`)
      .then(data => data.text())
      .then(html => x.innerHTML = html)
  });
```
