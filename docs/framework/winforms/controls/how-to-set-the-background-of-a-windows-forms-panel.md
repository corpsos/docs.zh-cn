---
title: 如何：设置 Windows 窗体面板的背景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: ff0c748cfb7b38c41b2ede211aed7bf6e6f68544
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534782"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>如何：设置 Windows 窗体面板的背景
Windows 窗体<xref:System.Windows.Forms.Panel>控件可以显示背景色和背景图像。 <xref:System.Windows.Forms.Control.BackColor%2A>属性设置为包含的控件，如标签和单选按钮的背景色。 如果<xref:System.Windows.Forms.Control.BackgroundImage%2A>未设置属性，<xref:System.Windows.Forms.Control.BackColor%2A>选择将填充整个面板。 如果<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性设置，则将在包含控件的后面显示的图像。  
  
### <a name="to-set-the-background-programmatically"></a>以编程方式设置背景  
  
1.  设置面板的<xref:System.Windows.Forms.Control.BackColor%2A>属性类型的值<xref:System.Drawing.Color?displayProperty=nameWithType>。  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2.  设置面板的<xref:System.Windows.Forms.Control.BackgroundImage%2A>属性使用<xref:System.Drawing.Image.FromFile%2A>方法<xref:System.Drawing.Image?displayProperty=nameWithType>类。  
  
    ```vb  
    ' You should replace the bolded image   
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image   
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Panel 控件](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panel 控件概述](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)
