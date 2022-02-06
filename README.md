> This is an example of the new [versioning][1] feature of
[Docurial][2].

  [1]: https://khanhduy1407.github.io/docurial/setup/setting-up-versioning/
  [2]: https://khanhduy1407.github.io/docurial/

## How to set up versioning

First, install [Docurial][3] and [dvci][4]:

```
pip install docurial
pip install dvci
```

  [3]: https://khanhduy1407.github.io/docurial/
  [4]: https://github.com/khanhduy1407/dvci

Next, set up your documentation project:

```
docums new .
```

Update `docums.yml`:

``` yaml
site_name: My Docs
theme:
  name: material
extra:
  version:
    provider: dvci
```

Make a change to `docs/index.md`, and publish the first version:

```
dvci deploy --push --update-aliases 0.1 latest
```

Set the default version to `latest`

```
dvci set-default --push latest
```

Now, make another change and publish a new version:

```
dvci deploy --push --update-aliases 0.2 latest
```
