# [beta] Markdown Syntax Highlighting for Notepad++

> :warning: **Warning**
>
> This branch `feature/emphasis-multiple-words` is still in beta.
> If you want trouble-free that do not mess up your existing markdown color schemes, please stick to [master branch][this_repo] as stable version.

This beta version will fix a limitation of *multiple em words*

However, due to limitation in UDL of Notepad++, it need to sacrifice bullet points by \* (asterisks) keyword.

I still need time to confirm if **this version will mess up other things?** Please kindly evaluate it. :)

In short:

|   | Stable (master branch) | Beta (this branch) |
|---|---|---|
| \*multiple em words\* | only parse the first word | parse ALL words |
| \* bullet points | fully support | not support (use \- or \+ instead) |

## Test and Vote

| Stable (master branch) | Beta (this branch) |
| --- | --- |
| ![stable](/test_stable_master.png) | ![beta](/test_beta_feature.png) |

- Each "theme" directory contains a XML file. The **filename and scheme name are same as that in master branch**.
- Make sure to re-open Notepad++ to take effect.
- In this branch, here is a file for testing: [test_beta.md](test_beta.md)

Which one do you prefer?

> If you like, welcome to vote in [this post @ Google+ NPP community](https://plus.google.com/+Edditoria/posts/dhgfRS3B7j4?sfc=true).

## Fix and Pull Request

If you can fix all the problem, or if you have an idea, please rise an issue for discussion.

For pull request, please do to this branch instead of master (which will stay in stable release).

Thanks!

-----------

## Build Script for Developers

In v1.1, a build script is provided for your convenience. It will follow the naming convention. It requires `bash` and `mustache.js` to run.

![A Build Script To Help You Build Color Scheme][build_screen]

When you run at the first time:

```shell
# Check if mustache.js is able to run in current bash
mustache -v

# Check if the script works
source build.sh --help
```

Build workflow:

1. Build a new color scheme: `source build.sh [new_name]` (no space, e.g. awesome_dark)
1. The script will create a new json file in a new folder:

  ![Build script demo step 2][build_screen_2]

1. In the json file:
  - Change the name according to the theme, e.g. "Markdown (Awesome Dark)"
  - Add your prefered colors in the empty strings, e.g. "FFFFFF"
  
  ![Build script demo step 3][build_screen_3]
  
1. Build a XML file: `source build.sh [new_name]`

  > tips: Press :arrow_up: to show your previous command.
  
1. A new XML file is ready to serve in the root directory of this repo.
1. Import in Notepad++ for testing. It's cool, right?

  > tips: Since the old XML is not overwritten, you can prepare two files in NPP.
  
1. Move the XML file into the corresponding theme folder. Done!

## Contribution

*tl;tr* For pull request, please do check **Allow edits from maintainers**, and merge from **your new branch** into **my master branch**; Or, propose a file change in Github directly; Or, hit me a message via issue page or my social contacts.

For details, please kindly read [CONTRIBUTING.md](CONTRIBUTING.md).

:beer: Thank you so much! :pray:

## Note to Original Repo from [@thomsmits][thomsmits_npp]

Basically I revised the original repo from scratch.  
If you don't feel good in my settings, please comment.  
I'll try my best to improve.  
Or, use Thomsmits' current repo :)

## License

Copyright for portions of [this repository][this_repo] are held by Thomas Smits, 2010 as part of [his repository][thomsmits_npp]. All other copyright are held by Edditoria, 2012-2017.

See the [LICENSE](LICENSE.md) file for license rights and limitations (MIT).


[screen_default]: /default_theme/markdown_npp_default_theme_screenshot.png "Markdown in Default Theme of Notepad++"
[screen_zenburn]: /zenburn_theme/markdown_npp_zenburn_screenshot.png "Markdown in Zenburn Theme of Notepad++"
[screen_blackboard]: /blackboard_theme/markdown_npp_blackboard_screenshot.png "Markdown in Blackboard Theme of Notepad++"
[screen_deep_black]: /deep_black_theme/markdown_npp_deep_black_screenshot.png "Markdown in Deep Black Theme of Notepad++"
[default_xml]: https://raw.githubusercontent.com/Edditoria/markdown-plus-plus/master/default_theme/userDefineLang_markdown.xml
[zenburn_xml]: https://raw.githubusercontent.com/Edditoria/markdown-plus-plus/master/zenburn_theme/userDefineLang_markdown_zenburn.xml
[blackboard_xml]: https://raw.githubusercontent.com/Edditoria/markdown-plus-plus/master/blackboard_theme/userDefineLang_markdown_blackboard.xml
[deep_black_xml]: https://raw.githubusercontent.com/Edditoria/markdown-plus-plus/master/deep_black_theme/userDefineLang_markdown_deep_black.xml

[this_repo]: https://github.com/Edditoria/markdown-plus-plus
[coffeescript]: https://github.com/Edditoria/coffeescript_npp_zenburn
[thomsmits]: https://github.com/thomsmits/markdown_npp
[thomsmits_npp]: https://github.com/thomsmits/markdown_npp
[test_file]: https://raw.githubusercontent.com/Edditoria/markdown-plus-plus/master/test.md

[build_screen]: /build/build_script_screenshot.png "A Build Script To Help You Build Color Scheme"
[build_screen_2]: /build/build_script_screenshot_2.png "Build script demo step 2"
[build_screen_3]: /build/build_script_screenshot_3.png "Build script demo step 3"
