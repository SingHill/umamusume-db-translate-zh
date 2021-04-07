[![Github Pages](https://github.com/HorizonKinen/umamusume-db-translate-zh/actions/workflows/master.yml/badge.svg)](https://github.com/HorizonKinen/umamusume-db-translate-zh/actions/workflows/master.yml)

*本储存库是[上游](https://github.com/FabulousCupcake/umamusume-db-translate)的****简体中文****翻译版本。If you need* ***English*** *version, check [upstream repo](https://github.com/FabulousCupcake/umamusume-db-translate) out!*

本项目旨在创建一个静态网页工具，通过生成翻译后的 `master.mdb` 文件以打补丁的方式对 [ウマ娘 プリティーダービー][1] 进行客户端翻译。这种方法很适用于 DMM 版本的 PC 客户端。

它使用 [`sql.js`][2] 直接在 Web 浏览器中生成翻译后的 `master.mdb` 文件。

## 使用

进入 https://horizonkinen.github.io/umamusume-db-translate-zh/ 上传你的 `master.mdb` 文件来获得翻译后的数据文件，随后根据网页上的指示进行下一步操作。

The **English** version can be accessed at https://fabulouscupcake.github.io/umamusume-db-translate/.

## 贡献

如果你有兴趣帮助该项目！欢迎你随时发起 pull request。

If you want to contribute the **English** translation, check [upstream repo](https://github.com/FabulousCupcake/umamusume-db-translate) out!

原文以 `.csv` 格式存放在 [`src/data/`][3]。

所有 `.csv` 文件都将被合并成一个 `json` 文件，并用于在 `master.mdb` 的 `text_data` 表中进行替换。

## 开发

生成最终的静态页面，需要使用 `Makefile`。 *注意：你需要安装 `jq`。*

如果想本地调试项目，你需要使用 [`serve`][4] 在本地运行一个 Web 服务。

```sh
$ make
==> Cleaning project…
==> Converting csv files into a single json…
==> Building static page…
==> Done!

$ npx serve public
┌───────────────────────────────────────────────────┐
│                                                   │
│   Serving!                                        │
│                                                   │
│   - Local:            http://localhost:5000       │
│   - On Your Network:  http://192.168.1.1:5000     │
│                                                   │
│   Copied local address to clipboard!              │
│                                                   │
└───────────────────────────────────────────────────┘

```

[1]: https://umamusume.jp
[2]: https://github.com/sql-js/sql.js
[3]: https://github.com/HorizonKinen/umamusume-db-translate-zh/tree/main/src/data
[4]: https://www.npmjs.com/package/serve
