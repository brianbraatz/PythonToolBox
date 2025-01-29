---
Description: "What Python code analysis tools are you using? : r/Python"
Notes: Pylance on vscode. I just turned on strict mode  and now everything Ive ever written is apparently wrong and bad and terrible and an error.
author: juli1
Url: https://www.reddit.com/r/Python/comments/xef3u2/what_python_code_analysis_tools_are_you_using/
Created: 2025-01-29  03:11:31
Modified: 
tags:
---

# What Python code analysis tools are you using? : r/Python

source: https://www.reddit.com/r/Python/comments/xef3u2/what_python_code_analysis_tools_are_you_using/

> ## Excerpt
> Pylance on vscode. I just turned on strict mode  and now everything Ive ever written is apparently wrong and bad and terrible and an error.

---
Pylance on vscode. I just turned on strict mode and now everything Ive ever written is apparently wrong and bad and terrible and an error.

Same I’m glad to see there are others like me

[![u/Spoiled_Kitten- avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/Spoiled_Kitten-/)

[![u/CluelessBot_ avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/CluelessBot_/)

what do you mean i cannot name my variable "codel" it's a list of very useful codes

[More replies](https://www.reddit.com/r/Python/comments/xef3u2/comment/iohd6fc/)

\`black\` will provide code fixes.

I lint everything when I run tox

Flake8, black, Mypy, isort.

Use black. Pretty good for most part. Sometimes wraps lines in a weird way though. I'd rather the line be 100ch than have unreadable wrapped lines

[![u/Damacustas avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_2.png)](https://www.reddit.com/user/Damacustas/)

You can set the maximum line length with the “— line-length” parameter

[![u/juli1 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/juli1/)

Isn't black about code formatting only?

[More replies](https://www.reddit.com/r/Python/comments/xef3u2/comment/ioi8ba4/)

lineprofiler is good for analyzing performance and identifying bottlenecks. (Not sure if that’s what you had in mind.)

[![u/Spoiled_Kitten- avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/Spoiled_Kitten-/)

[More replies](https://www.reddit.com/r/Python/comments/xef3u2/comment/ioglthk/)

Check out libcst and fixit

[![u/juli1 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/juli1/)

Checked it, super interesting! Thank you!

[More replies](https://www.reddit.com/r/Python/comments/xef3u2/comment/ioi0th3/)

I've lately been doing a meta-programming project. Yes, I know it's bad form. I don't care.

Python linters cower at the feet of my creation and weep tears of unknowable grief at their inability to parse my code.

[![u/AlexanderKotevski avatar](https://styles.redditmedia.com/t5_aypyv/styles/profileIcon_82vqo2bp7s7d1.jpg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=622fddf5f304dd9ea6d537cf3b8a80e40fe24016)](https://www.reddit.com/user/AlexanderKotevski/)

I use it on a daily basis. You get used to it's flaws. Shit it's like marriage or something

[More replies](https://www.reddit.com/r/Python/comments/xef3u2/comment/ioj2bd1/)

[![u/benefit_of_mrkite avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_6.png)](https://www.reddit.com/user/benefit_of_mrkite/)

 [![u/james_pic avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/james_pic/)

 ![Profile Badge for the Achievement Top 1% Commenter](https://i.redd.it/qwkcwa2zi3yd1.png) Top 1% Commenter

I haven't actually used it myself, but I gather CodeQL is a common next step for projects that like Bandit but want to take it to the next level.

I find myself spending too much time on reformatting my code when there is something highlighted in red by VSCode... I clearly see the benefit while working with a large codebase but for initial development and prototyping this is such a pain 😓

Sourcery is rather nice. Of course, just like any other analyser, not everything it finds is relevant. Use your own wisdom.

[![u/OlalekanA avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/OlalekanA/)

I use a combo of flake8, bandit, and sonaqube on the CI, sourcery with pycharm.

Black Autoflake iSort Pylint Flake8 Pydocstyle Bandit Commitizen

Everything running under the very useful pre-commit hooks.

I use print() for debugging. Since the '70s.

What do you think about github copilot? I would like to try it but haven't had time so far (I currently mostly code in R within r studio)

Hi mate,

Check this out; [https://zcloud.crayz.ee](https://zcloud.crayz.ee/)

It is free, and you will not loose time trying to configure it. It is using Sonarqube on the BE.

[![u/juli1 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/juli1/)

If it's using Sonarqube, why won't I use Sonarcloud instead?

It has all the community plugins already installed for you, cpp check, .net core etc It has its own structural code quality checker for C++ It has enterprise grade portfolio dashboard which you can only find in Sonar Enterprise edition. If you are not into these type of tools, we help you onboard quickly.

[More replies](https://www.reddit.com/r/Python/comments/xef3u2/comment/iqmlmla/) [More replies](https://www.reddit.com/r/Python/comments/xef3u2/comment/iq9oymq/)
