Git log => turbo mode

Today I learned that I can combine `-S 'my-search'` and `-p` in `git log` command. Here is an example:

```shell
git log -p -S 'create_or' app/models/*.rb
```

command dissecting:

- `-p` =&gt; equivalent to `git diff` for each commit found on log
- `-S 'my-seach'` =&gt; filtering by commits that **add/remove this content**

viniciusnegrisolo
June 22, 2016
