> -  原文地址：[How to Fix the "Item Not Found" Windows Error When Deleting a File or Folder](https://www.freecodecamp.org/news/how-to-solve-item-not-found-windows-error-deleting-file-folder/)
> -  原文作者：[Md. Fahim Bin Amin](https://www.freecodecamp.org/news/author/fahimbinamin/)
> -  译者：
> -  校对者：

![How to Fix the "Item Not Found" Windows Error When Deleting a File or Folder](https://www.freecodecamp.org/news/content/images/size/w2000/2022/04/Email_woman1.jpg)

If you use a Windows operating system, then you might have gotten this error before when trying to delete a file or folder.

It happens when, even though the file or folder is there, Windows says that it is failing to delete it because it can't find that file/folder in that directory.

This has also happened to me. In fact, I have faced this issue quite often. And tonight was no different.

I was trying to delete a folder, but couldn't do it. Each time I was trying to delete the folder, Windows was giving me a prompt saying "**This is no longer located in \[location\]. Verify the item's location and try again.**"

I tried all of the methods I could find to solve the issue, but nothing worked.

At last, I was successful and solved the issue. So, I thought why not share the trick I discovered with others? So, here you go!

![Screenshot-2022-04-14-225801](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-225801.png)

[Image source: D Studios Media](https://www.youtube.com/watch?v=u4IQCZ5dKMw)

If you have read [my other articles on freeCodeCamp](https://www.freecodecamp.org/news/author/fahimbinamin/), then you should know that I always use images from my own computer. So, if you are wondering why I am sharing an image from another source, don't worry – you will get the answer right now!

As I was trying to solve the issue so that I can safely delete the folder I wanted to delete, I was trying various methods out. At last, I solved the issue, and I think you might guess what I mean here: the folder got deleted successfully!

As the folder had been deleted, I could not take any screenshots of it. So I failed to collect the screenshot before deleting the folder.

That's why I used an image from another source above. 😅

## How to Fix the "Item Not Found" Windows Error

Now, let me show you how can you also solve this issue on your Windows operating system. Don't worry as I am going to show you every step from my own computer.

Suppose, I have a folder like the below which is not getting deleted however I try to delete it.

![Screenshot-2022-04-14-230359](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-230359.png)

So, I will use a special trick where I will use the terminal to delete this folder safely.

Open the CMD as Administrator. For that, simply click the Windows button, and search for **CMD**.

![Screenshot-2022-04-14-230529](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-230529.png)

Now right click on the **Command Prompt**, and click **Run as administrator**.

![Screenshot-2022-04-14-230710-1](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-230710-1.png)

The CMD will open with the privileges of an administrator.

![Screenshot-2022-04-14-232004](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-232004.png)

Now, we need to use the command, `rd /s "\\?\path`. In the path, you need to enter the folder address.

You can get the folder address or directory in various ways. I am going to show you two ways below.

**First way:** Right click on the folder/file, and click properties.

![Screenshot-2022-04-14-231044](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-231044.png)

Here, you will get the directory address.

![Screenshot-2022-04-14-231156](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-231156.png)

You have to add the folder name after that. For example, here my directory is: `C:\Users\FBA\Desktop` and the name of the folder I want to delete is `This Folder Is Not Getting Deleted`. So, the full directory address I need to use in the terminal will be: `C:\Users\FBA\Desktop\This Folder Is Not Getting Deleted`.

**Second way:** Go into the folder where you want to delete the folder/file, and you will get the directory address there.

![Screenshot-2022-04-14-231450](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-231450.png)

Simply click on the address, and copy the whole address. You can also use `Ctrl` + `C` as the shortcut.

![Screenshot-2022-04-14-231537](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-231537.png)

Anyway, after this, I have the directory address. Now I need to use the full command, `**rd /s "\?\C:\Users\FBA\Desktop\This Folder Is Not Getting Deleted**` on the terminal and I need to press the Enter key after that.

![Screenshot-2022-04-14-233359](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-233359.png)

Now I need to type Y and hit the Enter key.

![Screenshot-2022-04-14-233408](https://www.freecodecamp.org/news/content/images/2022/04/Screenshot-2022-04-14-233408.png)

Voilà! The folder is now gone. 😎

You can learn more about this rd command from [the official Microsoft Docs](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/rd).

In that way, you can safely delete any folder/file that won't get deleted using the regular method.

## Conclusion

Thanks for reading the entire article. If it helps you, then you can also check out other articles of mine at [freeCodeCamp](https://www.freecodecamp.org/news/author/fahimbinamin/).

If you want to get in touch with me, then you can do that using [Twitter](https://twitter.com/Fahim_FBA), [LinkedIn](https://www.linkedin.com/in/fahimfba/), [GitHub](https://github.com/FahimFBA), [English YouTube channel](https://www.youtube.com/channel/UCG97GCUifMS2Vm28tgXQi0Q), or [Bengali YouTube channel](https://www.youtube.com/channel/UCEF4lxmpBKV2oYCSFH6ExIQ).

💫 If you want to check my highlights, then you can do so at my [Polywork timeline](https://www.polywork.com/fahimbinamin).

Thanks a bunch! 😊