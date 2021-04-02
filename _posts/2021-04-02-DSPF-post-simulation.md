---
layout: post
title: 版图抽取DSPF网表进行仿真
categories: [cadence]
description: 
keywords: post simulation , dspf
---
1. Layout XL/L  界面 -> calibre -> run PEX, 进入PEX 设置界面
 
2. 按照下图设置界面中的inputs & outputs 选项。 注意 inputs 界面勾选 " export from layout viewer ", 其余根据自己的 library 和 cell 设置。

![PEX DSPF inputs setting](/images/posts/cadence/pex-dspf-inputs-setting.png)

 在 outputs 界面，需要修改 extraction type 为 R + C + CC，并且netlist format 需要修改为dspf)
 
![PEX  DSPF outputs setting](/images/posts/cadence/pex-dspf-outputs-setting.png)

3. 选择PEX options window:  在 lvs options Tab 加入 power & ground nets 的名字； 在connect Tab 里勾选“Don't connect nets by name"

4. Run PEX , 得到带有寄生参数网表的文件。 选择 save as, 保存该文件至自己设置的位置。

5. 打开准备用于后仿的 test circuit -> ADE L, 通过 analysis 和 output 进行和前仿一样设置

6. 在 ADE L 界面上选择 Setup->simulation files-> parasitic files(DSPF)-> 选中你所保存的文件-> DSPF options 中select 所替代的元器件，点OK。

![ADEL DSPF simulation files setting](/images/posts/cadence/dspf-simulation-files-setting.PNG)

7. 配置完成，可以进行仿真了。


