---
layout: post
title: Omnisharp in visual studio code crashes while opening an asp.net core project
---

Opening an asp.net core project on visual studio code for mac was resulting in an error.

```
Microsoft.Build.Exceptions.InvalidProjectFileException: The imported project "/usr/local/Cellar/mono/5.12.0.226/lib/mono/xbuild/15.0/Microsoft.Common.props" was not found.
```

Turns out the mono installs via homebrew were interfering with omnisharp trying to load the asp.net core project.

```
→ brew uninstall mono
Uninstalling /usr/local/Cellar/mono/5.12.0.226... (3,088 files, 353.5MB)
mono 4.8.0.524, 4.6.0.245, 4.4.1.0, 5.0.1.1, 4.4.2.11, 4.2.1.102_1, 4.6.2.7, 5.4.1.6, 4.6.2.16, 5.0.0.100, 4.8.0.520, 4.6.1.5, 4.8.1.0, 4.2.2.30, 4.4.0.182 15 are still installed.
Remove all versions with `brew uninstall --force mono`
```

```
→ brew uninstall --force mono
Uninstalling mono... (26,446 files, 3.7GB)
```

Voila! no more errors with visual studio code opening an asp.net core project.
