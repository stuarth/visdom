<h1 align="center">

<strong>Visdom</strong>

[![Build Status](https://travis-ci.org/fefit/visdom.svg?branch=main)](https://travis-ci.com/github/fefit/visdom)
[![crates.io](https://img.shields.io/crates/v/visdom.svg)](https://crates.io/crates/visdom)
[![tag](https://img.shields.io/github/v/tag/fefit/visdom.svg?sort=semver)](https://github.com/fefit/visdom/tags)
[![codecov](https://codecov.io/gh/fefit/visdom/branch/main/graph/badge.svg)](https://codecov.io/gh/fefit/visdom)
[![Crates download](https://img.shields.io/crates/d/visdom.svg)](https://crates.io/crates/visdom)
[![GitHub license](https://img.shields.io/github/license/fefit/visdom)](https://github.com/fefit/visdom/blob/main/LICENSE)

</h1>
<h4 align="center">

[API Document](https://github.com/fefit/visdom/wiki/API-Document)&nbsp;&nbsp;&nbsp;&nbsp;
[Online Demos](http://visdom.suchjs.com/#doc)&nbsp;&nbsp;&nbsp;&nbsp;
[Performance](https://github.com/fefit/visdom/blob/main/performance/README.md)&nbsp;&nbsp;&nbsp;&nbsp;
[中文 API 文档](https://github.com/fefit/visdom/wiki/%E4%B8%AD%E6%96%87API%E6%96%87%E6%A1%A3)&nbsp;&nbsp;&nbsp;&nbsp;
[更新文档](https://github.com/fefit/visdom/blob/main/CHANGELOG.md)

</h4>
<p>
:house: A html parsing、node selecting and mutation library written in Rust, using APIs similar to <a href="https://www.jquery.com">jQuery</a>, left off the parts thoes only worked in the browserS(e.g. render and event related methods).

It's not only helpful for the working with web scraping, but also supported useful APIs to mutate `text` nodes, so you can use it to mix your html with dirty html fragement to keep away from web scrapers too. :sparkling_heart:

</p>

## Demo

```rust
use visdom::Vis;
use std::error::Error;

fn main()-> Result<(), Box<dyn Error>>{
  let html = r##"
    <!DOCTYPE html>
    <html>
      <head>
        <meta charset="utf-8" />
      </head>
      <body>
        <nav id="header">
          <ul>
            <li>Hello,</li>
            <li>Vis</li>
            <li>Dom</li>
          </ul>
        </nav>
      </body>
    </html>
  "##;
  // load html
  let root = Vis::load(html)?;
  let lis = root.find("#header li");
  let lis_text = lis.text();
  println!("{}", lis_text);
  // will output "Hello,VisDom"
  Ok(())
}
```

[Try it online](http://visdom.suchjs.com/#hello)

## Depedencies

- Html parser：[https://github.com/fefit/rphtml](https://github.com/fefit/rphtml)
- Html entity encoding and decoding：[https://github.com/fefit/htmlentity](https://github.com/fefit/htmlentity)

## Questions & Advices & Bugs?

Welcome to report [Issue](https://github.com/fefit/visdom/issues) to us if you have any question or bug or good advice.

## License

[MIT License](./LICENSE).
