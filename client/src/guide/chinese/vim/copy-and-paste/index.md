---
title: Copy and Paste
localeTitle: 复制和粘贴
---
# 在Vim中复制和粘贴

在Vim中，复制通常被称为“yanking”，并且粘贴保持不变。

### 命令键

用于在Vim中进行yanking和粘贴的键是：

*   `x`删除一个字符
*   `y`要猛拉
*   `p`在光标后放置/粘贴
*   `P`在光标前放/粘贴
*   `pp`放/过整行
*   `d`切
*   `dd`切一条线
*   `"`削减或猛冲到登记册

### 仿形

要猛拉或剪切，请键入`y`或`d` ，然后键入“文本对象”。这些描述了应该删除或删除多少文本。例如， `yw`复制一个单词， `d$`从光标删除到行尾。它们也可以在视觉模式下使用，按`v`并移动光标，然后按`d`删除选择内的所有文本。

### 寄存器

寄存器只是剪贴板的另一个名称。但与其他文本编辑器不同，Vim有许多这样的“剪贴板”。

要取消或删除到寄存器，请键入`"<register name><command>` （例如： `"ayw` to \[y\] ank \[w\] ord以注册`a` ）。由于显而易见的原因，寄存器名称只能是一个字符长（ `"m` `"M` ， `"3`是允许的，但`"mr` ， `"MyReg` ， `"MyRegisterName`不是）。当没有指定寄存器时存储的默认寄存器是`"`和可以在其他程序中访问的系统剪贴板是`+` 。您还可以使用小写字符访问寄存器并使用大写字符附加到寄存器。例如`"dyy`将当前行复制到`d`寄存器，输入`"D3yw`复制接下来的3个单词并将它们添加到已经存储在`d`单词中。

### 粘贴

粘贴可以在正常模式或插入模式下完成。 在正常模式下：

*   `p`光标后粘贴
*   `P`在光标前粘贴
*   `gp`在光标后粘贴并将光标移动到粘贴的末尾
*   `gP`在光标前粘贴，并将光标移动到粘贴的末尾

在插入模式下，键入`Ctrl-r`然后键入一个寄存器，通常是`"` ，这将从光标所在的寄存器中粘贴，并在粘贴后移动光标。