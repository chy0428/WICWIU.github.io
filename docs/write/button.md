
**Material for MkDocs** 은 다양한 버튼 기능을 제공합니다.

## Usage

### Adding buttons

버튼을 추가하려면 단순히 Markdown 에서 하이퍼링크를 추가하는 문법에 ``{: .md-button}` 을 덧붙이면 됩니다.

_Example_:

``` markdown
[Subscribe to our mailing list](#){: .md-button }
```

_Result_:

[Subscribe to our mailing list][4]{: .md-button }

  [2]: #attribute-list
  [3]: ../setup/changing-the-colors.md#primary-color
  [4]: javascript:app.dialog$.next("Done!")

### Adding primary buttons

배경이 채워진 버튼을 만드려면 버튼을 만드는 문법에 `.md-button` 와 `.md-button--primary` 을 추가하면 됩니다.

_Example_:

``` markdown
[Subscribe to our mailing list](#){: .md-button .md-button--primary }
```

_Result_:

[Subscribe to our mailing list][4]{: .md-button .md-button--primary }

  [5]: ../index.md

### Adding icon buttons

아이콘이 있는 버튼을 만들려면 다음과 같이 하면 됩니다.

_Example_:

``` markdown
[Submit :fontawesome-solid-paper-plane:](#){: .md-button .md-button--primary }
```

_Result_:

[Submit :fontawesome-solid-paper-plane:][4]{: .md-button .md-button--primary }

  [6]: icons-emojis.md#using-icons
  [7]: https://github.com/squidfunk/mkdocs-material/tree/master/material/.icons
