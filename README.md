twypo
=====

Twig for TYPO3

## How to use it
1. `cd path/to/your/typo3conf/ext && git clone https://github.com/julianxhokaxhiu/twypo.git --recursive`
2. Install/Enable the "Twypo" extension inside your Backend
3. In `Include static (from extensions):` of your main template add the voice `Twypo: Default Setup`.
4. Refresh your page and you're done.

## Is it ready for production?
Nope, it's not.

But it's a Kickstart that a lot of guys at [cron IT GmbH](http://www.cron.eu) helped me on starting this project.

## Why?
Simply because there were a lot of POC but none of them was a working extension like "drop-in and run". So, this is my own effort to bring this kind of logic to the people that want to use it.

## What can you do for me?
If you're a TYPO3 developer, you can help me to scrape the data from the system to arrays/dictionaries. Also, the backend should be extended to give the user the choice of which template to use per page.

If you're a user, then just wait for it to be ready.

## Which is the license of this project?
I like the MIT license. Just use it as you like, but remember to keep the original author(s) in your source code files. Read the [LICENSE](https://github.com/julianxhokaxhiu/twypo/blob/master/LICENSE) file for more information.

## Reference

The namespace used for the returned collection on the view, is based on the default empty installation of typo3.

You can change some of them (ex. left, middle, etc.) using the TypoScript configuration. See `TWYPO_COLUMN_MAPPING` in [setup.txt](https://github.com/julianxhokaxhiu/twypo/blob/master/Configuration/TypoScript/setup.txt#L94).

Also the main layout entrypoint will be decided through the Layout option of the current page on the backend. To see which file will be called, based on that option, see `TWYPO_LAYOUT_MAPPING` in [setup.txt](https://github.com/julianxhokaxhiu/twypo/blob/master/Configuration/TypoScript/setup.txt#L105).

```
app
  menu // The website main menu
  page // The current page information (title, subtitle, etc.)
  content // The current items for the page.
    left // The left area of the current page
    middle // The middle area of the current page
    right // The right area of the current page
    border // The border area of the current page
```

If you want to know what's inside of it:

```
{{ dump(app) }}
```

or

```
{{ dump(app.menu) }}
```

If you want to see how these items are currently printed, see [index.twig](https://github.com/julianxhokaxhiu/twypo/blob/master/Resources/Private/Templates/index.twig).