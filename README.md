# stock-ticker

[![MELPA](http://melpa.org/packages/speed-type-badge.svg)](http://melpa.org/#/stock-ticker)

Emacs minor mode to show stock information in mode line.

![Screenshot](https://raw.github.com/hagleitn/stock-ticker/master/screen-shot-ticker.png)

Mode line will cycle through all the stock tickers you're interested
in, showing one at a time. Format is "ticker: price change (percent
change)"

Data is fetched from Yahoo's finance api via YQL.

## Installation

Install stock-ticker from [MELPA](melpa.org) with:

```
M-x package-install RET stock-ticker
```

If you prefer to install by hand: Put stock-ticker.el into a directory
specified by the load-path variable. Alternatively, you can add a
directory to the variable load-path by (add-to-list 'load-path
"ADDITIONAL-DIRECTORY").

If you put the file in "~/.emacs.d/stock-ticker/stock-ticker.el" for
instance, the following snipped in your .emacs file will load and init
the extension.

```lisp
(add-to-list 'load-path "~/.emacs.d/stock-ticker/stock-ticker.el")
(require 'stock-ticker)
```

```
M-x stock-ticker-global-mode
```

## Configuration

Here's how to turn stock ticker on in your .emacs:

```lisp
(stock-ticker-global-mode +1)
```

If you want to set your own stock tickers:

```lisp
(setq stock-ticker-symbols '("aapl" "goog" "fb"))
```

You can use regular stocks, but also funds, etc. Basically anything
that the Yahoo API supports (check: finance.yahoo.com).

Or add to the existing ones:

```lisp
(add-to-list 'stock-ticker-symbols "hdp")
(add-to-list 'stock-ticker-symbols "bcoix")
```

If you want to change the frequency with which the APIs are called for
new data:

```lisp
(setq stock-ticker-update-interval 600)
```

Finally, if you want to change how fast the symbols are cycled
through:

```lisp
(setq stock-ticker-display-interval 5)
```
